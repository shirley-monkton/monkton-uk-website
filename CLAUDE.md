# Monkton UK Website

## Website
https://monkton.digitalmonks.org

## Uploading Files

Upload files to the website using `curl` with WebDAV. All uploads go to the `/upload/` path.

**Credentials:**
- Username: `monkton`
- Password: `9aQgZnZNnBxhmpFvmvk36A==`

### Upload a file
```bash
curl -u monkton:'9aQgZnZNnBxhmpFvmvk36A==' -T myfile.png https://monkton.digitalmonks.org/upload/myfile.png
```

### Upload to a subdirectory
Create the directory first, then upload:
```bash
curl -u monkton:'9aQgZnZNnBxhmpFvmvk36A==' -X MKCOL https://monkton.digitalmonks.org/upload/images/
curl -u monkton:'9aQgZnZNnBxhmpFvmvk36A==' -T photo.jpg https://monkton.digitalmonks.org/upload/images/photo.jpg
```

### Delete a file
```bash
curl -u monkton:'9aQgZnZNnBxhmpFvmvk36A==' -X DELETE https://monkton.digitalmonks.org/upload/old-file.png
```

### List uploaded files
Visit https://monkton.digitalmonks.org/upload/ in a browser, or:
```bash
curl -u monkton:'9aQgZnZNnBxhmpFvmvk36A==' https://monkton.digitalmonks.org/upload/
```

## Rules
- All uploads MUST go under `/upload/` — that's the only writable path
- The rest of the site is publicly viewable, no auth needed to browse
- Maximum file size: 512MB
- Uploaded files are immediately available at their public URL (e.g. `https://monkton.digitalmonks.org/upload/myfile.png`)
