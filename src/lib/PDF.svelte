<script>

import { PDFDocument, rgb } from 'pdf-lib'
import fontkit from '@pdf-lib/fontkit'

const msg = "test"
let pdfBytes = {}

async function embedFontAndMeasureText() {
			// Fetch custom font
      const url = 'https://pdf-lib.js.org/assets/ubuntu/Ubuntu-R.ttf'
      const fontBytes = await fetch(url).then(res => res.arrayBuffer())

      // Create a new PDFDocument
      const pdfDoc = await PDFDocument.create()

      // Register the `fontkit` instance
      pdfDoc.registerFontkit(fontkit)

      // Embed our custom font in the document
      const customFont = await pdfDoc.embedFont(fontBytes)

      // Add a blank page to the document
      const page = pdfDoc.addPage()

      // Create a string of text and measure its width and height in our custom font
      const text = 'This is text in an embedded font!'
      const textSize = 35
      const textWidth = customFont.widthOfTextAtSize(text, textSize)
      const textHeight = customFont.heightAtSize(textSize)

      // Draw the string of text on the page
      page.drawText(text, {
        x: 40,
        y: 450,
        size: textSize,
        font: customFont,
        color: rgb(0, 0.53, 0.71),
      })

      // Draw a box around the string of text
      page.drawRectangle({
        x: 40,
        y: 450,
        width: textWidth,
        height: textHeight,
        borderColor: rgb(1, 0, 0),
        borderWidth: 1.5,
      })

      // Serialize the PDFDocument to bytes (a Uint8Array)
      pdfBytes = await pdfDoc.save()
      console.log(pdfBytes)

      // return pdfBytes
    }

  let pdfOutput = embedFontAndMeasureText()

</script>

{#await pdfOutput then pdfBytes}
<iframe src = {pdfBytes}></iframe>
<p>{msg}</p>
{/await}
