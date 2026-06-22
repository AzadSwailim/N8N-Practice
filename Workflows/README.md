# N8N Workflows

This folder contains the various workflow i have created.

Form Workflow

This is a form workflow where i have used on form submission trigger to get data from the user, the data is sent to an openAI node where chatGPT is used to draft emails and send it to the Gmail node. The Gmail node collects the content and sends it to the user.

⸻

Webhook

This workflow is similar to the form workflow but this uses a webhook where the data is taken from a HTML file, this HTML file gets information from the user. The POST method is used to transmit data in JSON to N8N to draft up an email and send it.

⸻

Web Scrapper

This is a workflow where a website is scrappped using HTTP request, the HTTP request gets the HTML of the website and uses openAI model to scrape the HTML code snippet, the output will be a string in JSON format. Then a code node is used to convert the single string into multiple JSON objects so that it can be entered into the google sheets.

Code used for converting the sting into JSON

const text = $input.first().json.output[0].content[0].text;
const books = JSON.parse(text);
return books.map(book => ({
    json: book
}));