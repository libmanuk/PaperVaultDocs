📰 Newspaper Viewer: Lightweight PDF Viewer

A streamlined newspaper viewer provides a fast, minimal interface for reading and interacting with newspaper issues. It is built using PHP and PDF.js, and renders content dynamically based on a structured ID passed via URL parameters.

📘 URL Format

Each newspaper issue is identified by a unique ID:

tttYYYYMMDDCC

ttt: 3-letter newspaper title code


YYYYMMDD: Publication date


CC: Copy number (2 digits)


Example:
 ada1923051801 → Adair County News, May 18, 1923, Copy 01
Viewer URL:
 https://kdnp.uky.edu/?id=ada1923051801

📁 System Architecture

The digital content is organized into two primary directories:

meta/: XML files containing metadata per issue
 → meta/ttt/tttYYYYMMDDCC.xml


pv/: PDF files for each newspaper issue
 → pv/ttt/tttYYYYMMDDCC/tttYYYYMMDDCC.pdf



🔧 Viewer Workflow

index.php reads the id parameter from the request.


Extracts the title code and issue ID.


Constructs file paths for both the PDF and XML metadata.


Loads and displays:


PDF content using PDF.js


Metadata (title, date, etc.) from XML



🛠️ Viewer Features

High-speed PDF rendering (via PDF.js)


Metadata display (title, date, issue details)


Page searching with hit highlighting


Navigation tools: page turning, issue browsing


Clipping tool: select and export page sections as images (via html-to-image)


Display of title histories


Responsive and lightweight for quick load times



✅ Technical Notes

Requires a well-formed id in the request URL


Relies on consistent XML metadata schema


No database backend—file-driven for simplicity and performance


Designed for scalability and ease of maintenance
