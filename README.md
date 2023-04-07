# APS

import java.awt.*;
import java.awt.image.BufferedImage;
import javax.swing.*;
import java.io.File;
import java.io.IOException;
import javax.imageio.ImageIO;
import javax.lang.model.type.NullType;

public class aps {
    
    private static Component label;
    /**
     * @param args
     */
    public static void main(String[] args) {

        BufferedImage img = null;

        try {
            img = ImageIO.read(new File("Consumption Calculator.png"));
        } catch (IOException e) {
            e.printStackTrace();
        }

        JLabel label = new JLabel();

        JFrame aps = new JFrame();
        aps.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        aps.setSize(772, 1011);

        Image dimg = img.getScaledInstance(aps.getWidth(), aps.getHeight(), 
                Image.SCALE_SMOOTH);

        ImageIcon imageIcon = new ImageIcon(dimg);
        ((JLabel) label).setIcon(imageIcon);

        aps.setVisible(true);
        aps.add(label);
    }
}
