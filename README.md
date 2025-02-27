GPTStore.AI

Categories
GPTs
Creators
Actions
Daily Rank
Join Discord
Submit GPTs
Sign in
Toggle theme
Home
GPTs
Doc Maker: PDFs, Resumes, PowerPoints, Excel
Actions
POST
Create a document directly with HTML content
POST
Create a document indirectly by prompting a GPT model specialized for longform writing
POST
Create a presentation indirectly by prompting a GPT model specialized for generating long presentations
POST
Create Resume Endpoint
POST
Create a new spreadsheet
redocly logoAPI docs by Redocly
Doc Maker GPT (v1)
Download OpenAPI specification:Download

A GPT that allows users to create documents.

Create a document directly with HTML content
Create a document directly with HTML content.

REQUEST BODY SCHEMA: application/json
required
content
required
string (Content)
Content of the document in HTML format

title
required
string (Title)
Title of the document.

Responses
200
Successful Response

422
Validation Error


POST
/create_document_directly_with_html
Request samples
Payload
Content type
application/json

Copy
{
"content": "string",
"title": "string"
}
Response samples
200422
Content type
application/json

Copy
null
Create a document indirectly by prompting a GPT model specialized for longform writing
Create a document indirectly by prompting a GPT model specialized for longform writing

REQUEST BODY SCHEMA: application/json
required
language	
string (Language)
Default: "en"
The two-digit ISO 639-1 code representing the expected human language for the document content.

openaiFileIdRefs	
Array of any (Openaifileidrefs)
Default: []
List of files to use during document generation, such as images or PDF / DOCX / PPTX files for downstream GPT to use for writing document. Each object contains: name - name of the file; id - identifier for the file; mime_type - mime type of the file; download_link - the URL to fetch the file.

pageCount	
integer (Pagecount)
Default: 5
The number of document pages (or number of presentation slides) to generate.

prompt
required
string (Prompt)
Instructions that will be used by a GPT-3.5 model to create the document. The instructions should be detailed and contain important information.

Responses
200
Successful Response

422
Validation Error


POST
/create_document_indirectly_with_gpt
Request samples
Payload
Content type
application/json

Copy
Expand allCollapse all
{
"language": "en",
"openaiFileIdRefs": [ ],
"pageCount": 5,
"prompt": "string"
}
Response samples
200422
Content type
application/json

Copy
null
Create a presentation indirectly by prompting a GPT model specialized for generating long presentations
Create a presentation indirectly by prompting a GPT model specialized for generating long presentations

REQUEST BODY SCHEMA: application/json
required
language	
string (Language)
Default: "en"
The two-digit ISO 639-1 code representing the expected human language for the document content.

openaiFileIdRefs	
Array of any (Openaifileidrefs)
Default: []
List of files to use during document generation, such as images or PDF / DOCX / PPTX files for downstream GPT to use for writing document. Each object contains: name - name of the file; id - identifier for the file; mime_type - mime type of the file; download_link - the URL to fetch the file.

pageCount	
integer (Pagecount)
Default: 5
The number of document pages (or number of presentation slides) to generate.

prompt
required
string (Prompt)
Instructions that will be used by a GPT-3.5 model to create the document. The instructions should be detailed and contain important information.

Responses
200
Successful Response

422
Validation Error


POST
/create_pptx_indirectly_with_gpt
Request samples
Payload
Content type
application/json

Copy
Expand allCollapse all
{
"language": "en",
"openaiFileIdRefs": [ ],
"pageCount": 5,
"prompt": "string"
}
Response samples
200422
Content type
application/json

Copy
null
Create Resume Endpoint
REQUEST BODY SCHEMA: application/json
required
prompt
required
string (Prompt)
Prompt used to describe the doc creation request. IT IS NOT USED TO CREATE DOC, only to display in UI for user to view later.

resume_content	
string (Resume Content)
Default: ""
Resume content in Markdown format. Do NOT include any of the above information (name, email, phone, location, website url) here; they should be directly placed via their respective fields. When using acronyms, ensure to write out the full term as well. For example, instead of writing 'SEO', write 'Search Engine Optimization (SEO)'.

resume_field_email	
string (Resume Field Email)
Optional: Personal email to be placed directly into the resume/cv. If supplied, do NOT include it in the formatted_markdown field.

resume_field_location	
string (Resume Field Location)
Optional: Location to be placed directly into the resume/cv. If supplied, do NOT include it in the formatted_markdown field.

resume_field_name	
string (Resume Field Name)
Default: ""
Mandatory: Personal name to be placed directly into the resume/cv. Do NOT include it in the formatted_markdown field.

resume_field_phone	
string (Resume Field Phone)
Optional: Phone number to be placed directly into the resume/cv. If supplied, do NOT include it in the formatted_markdown field.

resume_field_website_url	
string (Resume Field Website Url)
Optional: Website URL to be placed directly into the resume/cv. If supplied, do NOT include it in the formatted_markdown field.

title	
string (Title)
Default: "Untitled"
Mandatory: Title of the document.

Responses
200
Successful Response

422
Validation Error


POST
/create_resume
Request samples
Payload
Content type
application/json

Copy
{
"prompt": "string",
"resume_content": "",
"resume_field_email": "string",
"resume_field_location": "string",
"resume_field_name": "",
"resume_field_phone": "string",
"resume_field_website_url": "string",
"title": "Untitled"
}
Response samples
200422
Content type
application/json

Copy
null
Create a new spreadsheet
Create a new spreadsheet given data. Enclose all fields in double quotes.

REQUEST BODY SCHEMA: application/json
required
prompt
required
string (Prompt)
Prompt context for creating spreadsheet - will be shown later in document UI.

sheets
required
Array of objects (Sheets)
List of sheets inside spreadsheet. Each sheet consists of a header row, followed by rows of data

title	
string (Title)
Default: "Untitled"
Mandatory: the title of the spreadsheet. Must be included.

Responses
200
Successful Response

422
Validation Error


POST
/create_spreadsheet
Request samples
Payload
Content type
application/json

Copy
Expand allCollapse all
{
"prompt": "string",
"sheets": [
{}
],
"title": "Untitled"
}
Response samples
200422
Content type
application/json

Copy
null# GPT
