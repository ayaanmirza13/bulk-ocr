# Bulk OCR Extractor

A free browser-based OCR app for Android Chrome. It processes images locally with Tesseract.js and exports contacts to Excel with SheetJS.

## Run it
1. Upload this folder to a GitHub repository.
2. In GitHub, open Settings → Pages.
3. Select Deploy from a branch, choose `main` and `/ (root)`, then Save.
4. Open the published HTTPS URL in Chrome on Android.
5. Chrome menu (⋮) → Install app / Add to Home screen.

## Use
Choose multiple JPG/PNG/WebP photos (up to 500), start extraction, review/edit names and phone numbers, then download Excel.

## Important
- OCR is performed in the browser. Photos are not sent to a server by this app.
- The OCR and spreadsheet libraries load from jsDelivr CDN, so internet is required.
- For reliability on phones, process 50–100 images per batch and export between batches.
- Name suggestions are heuristic. Review flagged rows and verify phone numbers.
- This version uses English OCR. Hindi text and handwriting are not reliably supported.
