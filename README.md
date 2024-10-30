In Java, you can cut or crop images using the BufferedImage class. Here's a simple example demonstrating how to cut a portion of an image and save it as a new image file.


/*
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
*/

public class ImageCropper {

    public static void main(String[] args) {
        try {
            // Load the original image
            File inputFile = new File("path/to/your/image.jpg");
            BufferedImage originalImage = ImageIO.read(inputFile);

            // Define the area to crop (x, y, width, height)
            int x = 50; // Starting x coordinate
            int y = 50; // Starting y coordinate
            int width = 200; // Width of the cropped image
            int height = 150; // Height of the cropped image

            // Crop the image
            BufferedImage croppedImage = originalImage.getSubimage(x, y, width, height);

            // Save the cropped image
            File outputFile = new File("path/to/your/cropped_image.jpg");
            ImageIO.write(croppedImage, "jpg", outputFile);

            System.out.println("Image cropped successfully!");

        } catch (IOException e) {
            e.printStackTrace();
        } catch (RasterFormatException e) {
            System.out.println("Crop area is outside the bounds of the image.");
        }
    }
}
