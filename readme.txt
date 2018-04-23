# Doing PDF Diff (using Alpine on Docker)

  The program will make a comparison of 2 PDF files, and highlight the differences into png image file.

## Start docker container

  Let's start the alpine and put it into background.
  The name for the container will be *alpine-pdf-diff*.

  Make sure you run in the folder that you want the PDF files to be compared.
  And it will mount to /pdf folder in the Alpine.

  docker run --name alpine-pdf-diff -dt -v `pwd`:/pdf -w /pdf junyong/pdf-diff

  Change *`pwd`* to "%CD%" if you are running in windows environment.
  Using terminal that comes with the Docker toolbox is fine with `pwd`.
  
## Use PDF diff to compare 2 PDFs

  Go to the folder (stated above) that run the container.

  Now, let's say you want to compare RR-16898.pdf and RR-16900.pdf, run the following

  docker exec alpine-pdf-diff pdf-diff RR-16898.pdf RR-16900.pdf > diff.png

  diff.png will be generated in the current folder.
  Just open to view it, the difference will be highlighted using red color line or box.

 
