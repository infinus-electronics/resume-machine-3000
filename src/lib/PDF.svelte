<script>

import { PDFDocument } from 'pdf-lib'
import fontkit from '@pdf-lib/fontkit'

const pdfDoc = await PDFDocument.create()
pdfDoc.registerFontkit(fontkit)

</script>