package com.myproject39;

import java.io.File;
import net.sourceforge.tess4j.ITesseract;
import net.sourceforge.tess4j.Tesseract;
import net.sourceforge.tess4j.TesseractException;

public class ImageToTextApp {
    public static void main(String[] args) {
        if (args.length == 0) {
            System.out.println("વાપરવો: java -jar image-to-text-ai.jar <image-path>");
            return;
        }

        String imagePath = args[0]; // مثال: sample.png
        File imageFile = new File(imagePath);
        if (!imageFile.exists()) {
            System.err.println("Image file મળ્યો નથી: " + imagePath);
            return;
        }

        ITesseract tesseract = new Tesseract();

        // જો તમે tessdata અલગ પાથ પર રાખો તો uncomment અને યોગ્ય પાથ આપો:
        // tesseract.setDatapath("/usr/share/tesseract-ocr/4.00/tessdata");

        try {
            String text = tesseract.doOCR(imageFile);
            System.out.println("--------- Extracted Text ---------");
            System.out.println(text);
            System.out.println("--------- End ---------");
        } catch (TesseractException e) {
            System.err.println("OCR error: " + e.getMessage());
        }
    }
}
