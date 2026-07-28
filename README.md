TidyToolbox

tidytoolbox.online

Free browser based utilities that each do one job well. No accounts, no watermarks, no uploads. Every tool runs entirely on the visitor's own device, so files never touch a server.

Why

Most free online converters share the same three problems. They make you create an account before you can download anything. They stamp a watermark on the output, or hide the export behind a subscription. And they upload your files to somebody else's server to do work that a modern browser can do locally in a fraction of a second.

That last one bothered me most. Turning a photo of your passport into a PDF should not involve sending your passport to a company you have never heard of.

TidyToolbox does all the processing client side. Nothing is uploaded, nothing is stored, and there is no backend to leak anything in the first place.

Tools
Tool	What it does
Photo to PDF	Combine JPG or PNG images into a single PDF. Drag in a whole folder, reorder pages, export
Image Converter	Convert between PNG, JPG, WEBP, BMP and ICO. Batch mode with ZIP download
QR Code Generator	Static QR codes that never expire, with unlimited scans. Bulk generation from a CSV
CV and Resume Maker	10 templates with and without photo, live preview, free PDF export
Photo to Text	OCR for printed text. Exports to an editable Word document or PDF
Signature Maker	Draw a signature or photograph one on paper. Outputs a transparent PNG
Text to Handwriting	Turn typed text into realistic handwritten pages on ruled or plain paper
Built with

Vanilla HTML, CSS and JavaScript. No framework, no build step, no backend.

A few libraries do the heavy lifting in the browser: jsPDF for PDF generation, Tesseract.js for optical character recognition, JSZip for batch downloads, and the Canvas API for everything image related.

Deployed as static files on Netlify.

Running it locally

Clone the repo and serve the folder over HTTP. Opening the files directly with file:// will break some tools, because a few libraries need a proper origin to load their workers.

bash
git clone https://github.com/YOUR_USERNAME/tidytoolbox.git
cd tidytoolbox
python3 -m http.server 8000

Then visit http://localhost:8000.

Structure

Each tool is a self contained page. There is no shared bundle and no routing layer, so a tool can be opened, read and understood on its own without tracing through the rest of the codebase.

index.html              Landing page
tools.html              All tools
qr-generator.html       One file per tool
photo-to-pdf.html
image-converter.html
cv-resume-maker.html
photo-to-text.html
text-to-handwriting.html
signature-maker/
blog/                   Guides and how to articles
assets/                 Shared CSS, icons, fonts
Design

Typography is Fraunces for headings and IBM Plex Mono for labels. The palette is a small fixed set: ink for text, a safelight red for actions, a scan blue for accents, on warm paper.

Contributing

Issues and pull requests are welcome. If you hit a bug, saying which browser and which tool goes a long way.

License

MIT
