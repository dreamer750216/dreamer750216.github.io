---
layout: post
title:  "fossology usage"
categories: Fossology
author: DreAmeR
description: fossology usage
---

###  **1. docker run**
>
docker run -p 8081:80 fossology/fossology  

###  **2. script ruby**
>
require 'rest-client'  
require 'json'  
require 'nokogiri'  
require 'base64'  
>
def do_get(url, headers)  
&nbsp;&nbsp;begin  
&nbsp;&nbsp;&nbsp;&nbsp;    r = RestClient.get url, headers  
&nbsp;&nbsp;&nbsp;&nbsp;    return r  
&nbsp;&nbsp;  rescue RestClient::ExceptionWithResponse => e  
&nbsp;&nbsp;&nbsp;&nbsp;    puts e.response  
&nbsp;&nbsp;  end  
end  
>
def do_post(url, payload, headers)  
&nbsp;&nbsp;  begin  
&nbsp;&nbsp;&nbsp;&nbsp;    r = RestClient.post url, payload, headers  
&nbsp;&nbsp;&nbsp;&nbsp;    return r  
&nbsp;&nbsp;  rescue RestClient::ExceptionWithResponse => e  
&nbsp;&nbsp;&nbsp;&nbsp;    puts e.response  
&nbsp;&nbsp;  end  
end  
>
def upload(token, url, folder_id, file_name)  
&nbsp;&nbsp;  payload = { multipart: true, fileInput: File.new(file_name, 'rb') }  
&nbsp;&nbsp;  headers = { Authorization: 'Bearer ' + token, folderId: folder_id }  
&nbsp;&nbsp;  r = do_post("#{url}/uploads", payload, headers)  
&nbsp;&nbsp;  JSON.parse(r)['message']  
end  
>
def analyze(token, url, folder_id, upload_id)  
&nbsp;&nbsp;  payload = '{"analysis":{"monk":true, "nomos":true, "copyright_email_author":true}}'  
&nbsp;&nbsp;  headers = { Authorization: 'Bearer ' + token, folderId: folder_id, uploadId: upload_id, content_type: :json}  
&nbsp;&nbsp;  do_post("#{url}/jobs", payload, headers)  
end  
>
def report(token, url, upload_id)  
&nbsp;&nbsp;  headers = { Authorization: 'Bearer ' + token, uploadId: upload_id, reportFormat: 'spdx2'}  
&nbsp;&nbsp;  r = do_get("#{url}/report", headers)  
&nbsp;&nbsp;  JSON.parse(r)['message'].split('/').last  
end  
>
def download_license(token, url, report_id)  
&nbsp;&nbsp;  headers = { Authorization: 'Bearer ' + token}  
&nbsp;&nbsp;r = do_get("#{url}/report/#{report_id}", headers)  
&nbsp;&nbsp;  report = Nokogiri::XML r.to_s  
&nbsp;&nbsp;  report.xpath('//spdx:licenseInfoInFile').each do |license|  
&nbsp;&nbsp;&nbsp;&nbsp;    return license.attr('rdf:resource')  
&nbsp;&nbsp;  end  
&nbsp;&nbsp;  return 'NA'  
end  
>
def info(filename)  
&nbsp;&nbsp;  url = 'http://fossology_server:8081/repo/api/v1'  
&nbsp;&nbsp;  token ='token'  
&nbsp;&nbsp;  folder_id = '1'  
&nbsp;&nbsp;  upload_id = upload(token, url, folder_id, filename)  
&nbsp;&nbsp;  sleep(5)  
&nbsp;&nbsp;  analyze(token, url, folder_id, upload_id)  
&nbsp;&nbsp;  report_id = report(token, url, upload_id)  
&nbsp;&nbsp;  sleep(5)  
&nbsp;&nbsp;  license = download_license(token, url, report_id)  
&nbsp;&nbsp;  copyright = download_copyright(token, url, report_id)  
&nbsp;&nbsp;  return [license, copyright]  
end  

<br/>
#### Thanks：
> 
[fossology-github][fossology]  

[fossology]: https://github.com/fossology/fossology
