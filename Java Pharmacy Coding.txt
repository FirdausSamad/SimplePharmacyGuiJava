import java.awt.*;
import javax.swing.*;
import javax.swing.border.*;
import java.awt.event.*;
import java.util.*;
import java.text.*;

public class Pharmacy extends JFrame implements ActionListener 
{
    private JLabel lblCashierName,lblPassword,lblIC;
    private JPasswordField password;
    private JTextField tfCashierName,tfIC;
    private JRadioButton rbMember, rbNonMember;
    private JCheckBox cbBena, cbTussidex, cbParacetamol, cbDyrito, cbZelox, cbMexomide;
    private JCheckBox cbHyomide, cbNazin, cbUphalyte, cbOriginal;
    private JCheckBox cb1, cb2, cb3, cb4, cb5, cb6, cb7, cb8, cb9, cb10; 
    private JTextField tfBena, tfTussidex, tfParacetamol, tfDyrito, tfZelox, tfMexomide;
    private JTextField tfHyomide, tfNazin, tfUphalyte, tfOriginal;
    private JTextField tf1, tf2, tf3, tf4, tf5, tf6, tf7, tf8, tf9, tf10;
    private JButton btnOk, btnClear, btnExit,btnClear2,btnSubmit,btnLogOut,btnExit2;
    private JPanel panelCashier , panelMember, pCustom,panelButton,panelReceipt, panelImage,panelR,panelM,panelB;
    private JTextArea taReceipt;
    private JScrollPane scroll;
   
    public static void main(String args[])
    {
        Pharmacy newJFrame = new Pharmacy();
        newJFrame.setVisible(true);
        newJFrame.setSize(1000,700);
        newJFrame.setLocation(0,0);
        newJFrame.setTitle("Pharmacy");
       
        JMenuBar mb = new JMenuBar();
        JMenu file  = new JMenu("File");
        JMenuItem quit = new JMenuItem("Exit");
        file.add(quit);
        //func(quit);
        
        mb.add(file);
         newJFrame.setJMenuBar(mb);
       
    }
    public void func(JMenuItem quit)
    {
        quit.addActionListener(this);
    }
    public Pharmacy()
    {
        
        Container c = getContentPane();
        c.setLayout(new GridLayout(5,1));
        //panel image
        panelImage = new JPanel(new GridLayout(1,1));
        JLabel image = new JLabel(new ImageIcon("siap1.jpg"));
        panelImage.add(image);
        c.add(panelImage);
        
        
        //panel cashier name
        
        lblCashierName = new JLabel("Pharmacist's Name : ");
        tfCashierName = new JTextField(10);
       
        lblIC = new JLabel("Pharmacist's IC No. : ");
        tfIC = new JTextField(10);
        
        lblPassword = new JLabel("Password : ");
        password = new JPasswordField(10);
        
        panelCashier = new JPanel(new GridLayout(3,1));
        panelCashier.setBorder(new TitledBorder("PHARMACIST"));
        panelCashier.add(lblCashierName);
        panelCashier.add(tfCashierName);
        panelCashier.add(lblIC);
        panelCashier.add(tfIC);
        panelCashier.add(lblPassword);
        panelCashier.add(password);
        
        c.add(panelCashier);
        
        //panel members
        rbMember = new JRadioButton("Member *5% Discount");
        rbNonMember = new JRadioButton("Non-Member");
        
        ButtonGroup bgroup = new ButtonGroup();
        bgroup.add(rbMember);
        bgroup.add(rbNonMember);
        
        panelMember = new JPanel(new GridLayout(1,2));
        panelMember.setBorder(new TitledBorder("MEMBERSHIP"));
        //panelMember.setBackground(Color.GRAY);
        panelMember.add(rbMember);
        panelMember.add(rbNonMember);
        
       
        
        btnExit2 = new JButton("EXIT");
        btnSubmit = new JButton("LOG IN");
        btnLogOut = new JButton("LOG OUT");
        btnClear2 = new JButton("CLEAR");
        panelB = new JPanel(new FlowLayout());
        panelB.setBorder(new TitledBorder("LOG IN"));
        //panelButton.setBackground(Color.RED);
        panelB.add(btnSubmit);
        
        panelB.add(btnLogOut);
        panelB.add(btnClear2);
        panelB.add(btnExit2);
        
        panelM = new JPanel(new GridLayout(1,2));
        panelM.add(panelB);
        panelM.add(panelMember);
        c.add(panelM);
        
        //panel Medicine
        
        cbBena = new JCheckBox(" Bena Expectorant");
        tfBena = new JTextField("*",2);
        cbTussidex = new JCheckBox (" Tussidex Forte");
        tfTussidex = new JTextField("*",2);
        cbParacetamol = new JCheckBox(" Paracetamol");
        tfParacetamol = new JTextField("*",2);
        cbDyrito = new JCheckBox(" Dyrito Tablet");
        tfDyrito = new JTextField("*",2);
        cbZelox = new JCheckBox(" Zelox-II");
        tfZelox = new JTextField("*",2);
        cbMexomide = new JCheckBox(" Mexomide Tablet");
        tfMexomide = new JTextField("*",2);
        cbHyomide = new JCheckBox(" Hyomide Tablet");
        tfHyomide = new JTextField("*",2);
        cbNazin = new JCheckBox(" Nazin Tablet");
        tfNazin = new JTextField("*",2);
        cbUphalyte = new JCheckBox(" Uphalyte Orange");
        tfUphalyte = new JTextField("*",2);
        cbOriginal = new JCheckBox(" Uphalyte Original");
        tfOriginal = new JTextField("*",2);
        cb1 = new JCheckBox(" Abacavir Sulfate");
        tf1 = new JTextField("*",2);
        cb2 = new JCheckBox(" Bionect Cream, Gel");
        tf2 = new JTextField("*",2);
        cb3 = new JCheckBox(" Cytogam");
        tf3 = new JTextField("*",2);
        cb4 = new JCheckBox(" Darvon Compound");
        tf4 = new JTextField("*",2);
        cb5 = new JCheckBox(" Eurax");
        tf5 = new JTextField("*",2);
        cb6 = new JCheckBox(" Fortesta");
        tf6 = new JTextField("*",2);
        cb7 = new JCheckBox(" Oxsoralen-Ultra");
        tf7 = new JTextField("*",2);
        cb8 = new JCheckBox(" Sulfasalazine Tablet");
        tf8 = new JTextField("*",2);
        cb9 = new JCheckBox(" Yellow Fever Vaccine");
        tf9 = new JTextField("*",2);
        cb10 = new JCheckBox(" Lidocaine");
        tf10 = new JTextField("*",2);
        
        pCustom = new JPanel(new GridLayout(4,10));
        pCustom.setBorder(new TitledBorder("MEDICINE [Fill quantity (*)]"));
        //pCustom.setBackground(Color.GRAY);
        
        pCustom.add(cbBena);
        pCustom.add(tfBena);
        pCustom.add(cbTussidex);
        pCustom.add(tfTussidex);
        pCustom.add(cbParacetamol);
        pCustom.add(tfParacetamol);
        pCustom.add(cbDyrito);
        pCustom.add(tfDyrito);
        pCustom.add(cbZelox);
        pCustom.add(tfZelox);
        pCustom.add(cbMexomide);
        pCustom.add(tfMexomide);
        pCustom.add(cbHyomide);
        pCustom.add(tfHyomide);
        pCustom.add(cbNazin);
        pCustom.add(tfNazin);
        pCustom.add(cbUphalyte);
        pCustom.add(tfUphalyte);
        pCustom.add(cbOriginal);
        pCustom.add(tfOriginal);
        pCustom.add(cb1);
        pCustom.add(tf1);
        pCustom.add(cb2);
        pCustom.add(tf2);
        pCustom.add(cb3);
        pCustom.add(tf3);
        pCustom.add(cb4);
        pCustom.add(tf4);
        pCustom.add(cb5);
        pCustom.add(tf5);
        pCustom.add(cb6);
        pCustom.add(tf6);
        pCustom.add(cb7);
        pCustom.add(tf7);
        pCustom.add(cb8);
        pCustom.add(tf8);
        pCustom.add(cb9);
        pCustom.add(tf9);
        pCustom.add(cb10);
        pCustom.add(tf10);
        c.add(pCustom);
        //panel button
        btnOk = new JButton("OK");
        btnExit = new JButton("EXIT");
        btnClear = new JButton("CLEAR");
        panelButton = new JPanel(new FlowLayout());
        panelButton.setBorder(new TitledBorder("PURCHASE"));
        //panelButton.setBackground(Color.RED);
        panelButton.add(btnOk);
        panelButton.add(btnClear);
        panelButton.add(btnExit);
        
        
        //panel receipt
        taReceipt = new JTextArea();
        taReceipt.setEditable(false);
        scroll = new JScrollPane(taReceipt);
        panelReceipt = new JPanel(new GridLayout(1,1));
        panelReceipt.setBorder(new TitledBorder("RECEIPT"));
        //panelReceipt.setBackground(Color.GRAY);
        panelReceipt.add(scroll);
        
        panelR = new JPanel(new GridLayout(1,2));
        panelR.add(panelButton);
        panelR.add(panelReceipt);
        c.add(panelR);
        
        //gune JtextArea
        //setEnabled
        //private JPanel panelCashier , panelMember, pCustom,panelButton,panelReceipt, panelImage,panelR,panelM,panelB;
        
       //private JRadioButton rbMember, rbNonMember;
    //private JCheckBox cbBena, cbTussidex, cbParacetamol, cbDyrito, cbZelox, cbMexomide;
    //private JCheckBox cbHyomide, cbNazin, cbUphalyte, cbOriginal;
    //private JCheckBox cb1, cb2, cb3, cb4, cb5, cb6, cb7, cb8, cb9, cb10; 
    //private JTextField tfBena, tfTussidex, tfParacetamol, tfDyrito, tfZelox, tfMexomide;
    //private JTextField tfHyomide, tfNazin, tfUphalyte, tfOriginal;
    //private JTextField tf1, tf2, tf3, tf4, tf5, tf6, tf7, tf8, tf9, tf10;
    //private JButton btnOk, btnClear, btnExit,btnClear2,btnSubmit;
    //private JPanel panelCashier , panelMember, pCustom,panelButton,panelReceipt, panelImage,panelR,panelM,panelB;
    //private JTextArea taReceipt;
        
       
        panelMember.setEnabled(false);
        pCustom.setEnabled(false);
        panelButton.setEnabled(false);
        panelReceipt.setEnabled(false);
        rbMember.setEnabled(false);
        rbNonMember.setEnabled(false);
        cbBena.setEnabled(false);
        cbTussidex.setEnabled(false);
        cbParacetamol.setEnabled(false);
        cbDyrito.setEnabled(false);
        cbZelox.setEnabled(false);
        cbMexomide.setEnabled(false);
        cbHyomide.setEnabled(false);
        cbNazin.setEnabled(false);
        cbUphalyte.setEnabled(false);
        cbOriginal.setEnabled(false);
        cb1.setEnabled(false);
        cb2.setEnabled(false);
        cb3.setEnabled(false);
        cb4.setEnabled(false);
        cb5.setEnabled(false);
        cb6.setEnabled(false);
        cb7.setEnabled(false);
        cb8.setEnabled(false);
        cb9.setEnabled(false);
        cb10.setEnabled(false);
        tfBena.setEnabled(false);
        tfTussidex.setEnabled(false);
        tfParacetamol.setEnabled(false);
        tfDyrito.setEnabled(false);
        tfZelox.setEnabled(false);
        tfMexomide.setEnabled(false);
        tfHyomide.setEnabled(false);
        tfNazin.setEnabled(false);
        tfUphalyte.setEnabled(false);
        tfOriginal.setEnabled(false);
        tf1.setEnabled(false);
        tf2.setEnabled(false);
        tf3.setEnabled(false);
        tf4.setEnabled(false);
        tf5.setEnabled(false);
        tf6.setEnabled(false);
        tf7.setEnabled(false);
        tf8.setEnabled(false);
        tf9.setEnabled(false);
        tf10.setEnabled(false);
        btnOk.setEnabled(false);
        btnClear.setEnabled(false);
        btnExit.setEnabled(false);
        taReceipt.setEnabled(false);
        //register the frame as an action listener of the events
        btnOk.addActionListener(this);
        btnExit.addActionListener(this);
        btnExit2.addActionListener(this);
        btnClear.addActionListener(this);
        btnSubmit.addActionListener(this);
        btnClear2.addActionListener(this);
        btnLogOut.addActionListener(this);
    }
    //to perform action
    public void actionPerformed(ActionEvent e )
    {
       DecimalFormat df = new DecimalFormat("0.00"); 
       double priceBena = 4, priceTussidex = 4, priceParacetamol = 2.5, priceDyrito = 2, priceZelox = 5; 
       double priceMexomide = 2.5, priceHyomide = 3, priceNazin = 4, priceUphalyte = 1.5, priceOriginal =1.5;
       double price1 = 6, price2 = 9, price3 = 7.5, price4 = 4, price5 = 8.5, price6 = 6.5, price7 = 2;
       double price8 = 1.5, price9 = 3.5, price10 = 2;
       
       //to find total
       double total = 0;
       int no = 0;
        //if click button ok
        if(e.getSource() == btnOk)
        {
            //to write in receipt
           taReceipt.setText("\t\t\tPHARMACY\n");
           taReceipt.append("\t\tPharmacist's Name : "+tfCashierName.getText()+"\n");
           taReceipt.append("\t\tMembership \t: ");
            if(rbMember.isSelected())
            {
                taReceipt.append("Member\n");
                taReceipt.append("\tNo\tItem\t\tQuantity\t\tPrice\n");
                
                if(cbBena.isSelected())
                {   
                    int Bena = Integer.parseInt(tfBena.getText());
                    no = no + 1;
                    double newPriceBe =(priceBena-(priceBena * 0.05))*Bena;
                    taReceipt.append("\t"+no+"\tBena Expectorant\t       "+ Bena+"\t\t"+df.format(newPriceBe)+"\n");
                    total = total + newPriceBe;
                }
                if(cbTussidex.isSelected())
                {   
                    int Tussidex = Integer.parseInt(tfTussidex.getText());
                    no = no + 1;
                    double newPriceTu =(priceTussidex-(priceTussidex * 0.05))*Tussidex;
                    taReceipt.append("\t"+no+"\tTussidex Forte\t\t       "+ Tussidex+"\t\t"+df.format(newPriceTu)+"\n");
                    total = total + newPriceTu;
                }
                if(cbParacetamol.isSelected())
                {   
                    int Paracetamol = Integer.parseInt(tfParacetamol.getText());
                    no = no + 1;
                    double newPricePa =(priceParacetamol-(priceParacetamol * 0.05))*Paracetamol;
                    taReceipt.append("\t"+no+"\tParacetamol\t\t       "+ Paracetamol+"\t\t"+df.format(newPricePa)+"\n");
                    total = total + newPricePa;
                }
                if(cbDyrito.isSelected())
                {
                    int Dyrito = Integer.parseInt(tfDyrito.getText());
                    no = no + 1;
                    double newPriceDy = (priceDyrito - (priceDyrito * 0.05))*Dyrito;
                    taReceipt.append("\t"+no+"\tDyrito Tablet\t\t       "+ Dyrito+"\t\t"+df.format(newPriceDy)+"\n");
                    total = total + newPriceDy;
                }
                if(cbZelox.isSelected())
                {   
                    int Zelox = Integer.parseInt(tfZelox.getText());
                    no = no + 1;
                    double newPriceZe =(priceZelox-(priceZelox * 0.05))*Zelox;
                    taReceipt.append("\t"+no+"\tZelox-II\t\t       "+ Zelox+"\t\t"+df.format(newPriceZe)+"\n");
                    total = total + newPriceZe;
                }
                if(cbMexomide.isSelected())
                {   
                    int Mexomide = Integer.parseInt(tfMexomide.getText());
                    no = no + 1;
                    double newPriceMe =(priceMexomide-(priceMexomide * 0.05))*Mexomide;
                    taReceipt.append("\t"+no+"\tMexomide Tablet\t       "+ Mexomide+"\t\t"+df.format(newPriceMe)+"\n");
                    total = total + newPriceMe;
                }
                if(cbHyomide.isSelected())
                {   
                    int Hyomide = Integer.parseInt(tfHyomide.getText());
                    no = no + 1;
                    double newPriceHy =(priceHyomide-(priceHyomide * 0.05))*Hyomide;
                    taReceipt.append("\t"+no+"\tHyomide Tablet\t\t       "+ Hyomide+"\t\t"+df.format(newPriceHy)+"\n");
                    total = total + newPriceHy;
                }
                if(cbNazin.isSelected())
                {   
                    int Nazin = Integer.parseInt(tfNazin.getText());
                    no = no + 1;
                    double newPriceNa =(priceNazin-(priceNazin * 0.05))*Nazin;
                    taReceipt.append("\t"+no+"\tNazin Tablet\t\t       "+ Nazin+"\t\t"+df.format(newPriceNa)+"\n");
                    total = total + newPriceNa;
                }
                if(cbUphalyte.isSelected())
                {   
                    int Uphalyte = Integer.parseInt(tfUphalyte.getText());
                    no = no + 1;
                    double newPriceUp =(priceUphalyte-(priceUphalyte * 0.05))*Uphalyte;
                    taReceipt.append("\t"+no+"\tUphalyte Orange\t       "+ Uphalyte+"\t\t"+df.format(newPriceUp)+"\n");
                    total = total + newPriceUp;
                }
                if(cbOriginal.isSelected())
                {   
                    int Original = Integer.parseInt(tfOriginal.getText());
                    no = no + 1;
                    double newPriceOr =(priceOriginal-(priceOriginal * 0.05))*Original;
                    taReceipt.append("\t"+no+"\tUphalyte Original\t       "+ Original+"\t\t"+df.format(newPriceOr)+"\n");
                    total = total + newPriceOr;
                }
                if(cb1.isSelected())
                {   
                    int n1 = Integer.parseInt(tf1.getText());
                    no = no + 1;
                    double newPrice1 =(price1-(price1 * 0.05))*n1;
                    taReceipt.append("\t"+no+"\tAbacavir Sulfate\t\t       "+ n1+"\t\t"+df.format(newPrice1)+"\n");
                    total = total + newPrice1;
                }
                if(cb2.isSelected())
                {   
                    int n2 = Integer.parseInt(tf2.getText());
                    no = no + 1;
                    double newPrice2 =(price2-(price2 * 0.05))*n2;
                    taReceipt.append("\t"+no+"\tBionect Cream, Gel\t       "+ n2+"\t\t"+df.format(newPrice2)+"\n");
                    total = total + newPrice2;
                }
                if(cb3.isSelected())
                {   
                    int n3 = Integer.parseInt(tf3.getText());
                    no = no + 1;
                    double newPrice3 =(price3-(price3 * 0.05))*n3;
                    taReceipt.append("\t"+no+"\tCytogam\t\t       "+ n3+"\t\t"+df.format(newPrice3)+"\n");
                    total = total + newPrice3;
                }
                if(cb4.isSelected())
                {   
                    int n4 = Integer.parseInt(tf4.getText());
                    no = no + 1;
                    double newPrice4 =(price4-(price4 * 0.05))*n4;
                    taReceipt.append("\t"+no+"\tDarvon Compound\t       "+ n4+"\t\t"+df.format(newPrice4)+"\n");
                    total = total + newPrice4;
                }
                if(cb5.isSelected())
                {   
                    int n5 = Integer.parseInt(tf5.getText());
                    no = no + 1;
                    double newPrice5 =(price5-(price5 * 0.05))*n5;
                    taReceipt.append("\t"+no+"\tEurax\t\t       "+ n5+"\t\t"+df.format(newPrice5)+"\n");
                    total = total + newPrice5;
                }
                if(cb6.isSelected())
                {   
                    int n6 = Integer.parseInt(tf6.getText());
                    no = no + 1;
                    double newPrice6 =(price6-(price6 * 0.05))*n6;
                    taReceipt.append("\t"+no+"\tFortesta\t\t       "+ n6+"\t\t"+df.format(newPrice6)+"\n");
                    total = total + newPrice6;
                }
                if(cb7.isSelected())
                {   
                    int n7 = Integer.parseInt(tf7.getText());
                    no = no + 1;
                    double newPrice7 =(price7-(price7 * 0.05))*n7;
                    taReceipt.append("\t"+no+"\tOxsoralen-Ultra\t\t       "+ n7+"\t\t"+df.format(newPrice7)+"\n");
                    total = total + newPrice7;
                }
                if(cb8.isSelected())
                {   
                    int n8 = Integer.parseInt(tf8.getText());
                    no = no + 1;
                    double newPrice8 =(price8-(price8 * 0.05))*n8;
                    taReceipt.append("\t"+no+"\tSulfasalazine Tablet\t       "+ n8+"\t\t"+df.format(newPrice8)+"\n");
                    total = total + newPrice8;
                }
                if(cb9.isSelected())
                {   
                    int n9 = Integer.parseInt(tf9.getText());
                    no = no + 1;
                    double newPrice9 =(price9-(price9 * 0.05))*n9;
                    taReceipt.append("\t"+no+"\tYellow Fever Vaccine\t       "+ n9+"\t\t"+df.format(newPrice9)+"\n");
                    total = total + newPrice9;
                }
                if(cb10.isSelected())
                {   
                    int n10 = Integer.parseInt(tf10.getText());
                    no = no + 1;
                    double newPrice10 =(price10-(price10 * 0.05))*n10;
                    taReceipt.append("\t"+no+"\tLidocaine\t\t       "+ n10+"\t\t"+df.format(newPrice10)+"\n");
                    total = total + newPrice10;
                }
            }                                                                                                              
            else if(rbNonMember.isSelected())
            {
                taReceipt.append("Non-Member\n");
                taReceipt.append("\tNo\tItem\t\tQuantity\t\tPrice\n");
                if(cbBena.isSelected())
                {   
                    int Bena = Integer.parseInt(tfBena.getText());
                    no = no + 1;
                    double newPriceBe =(priceBena)*Bena;
                    taReceipt.append("\t"+no+"\tBena Expectorant\t       "+ Bena+"\t\t"+df.format(newPriceBe)+"\n");
                    total = total + newPriceBe;
                }
                if(cbTussidex.isSelected())
                {   
                    int Tussidex = Integer.parseInt(tfTussidex.getText());
                    no = no + 1;
                    double newPriceTu =(priceTussidex)*Tussidex;
                    taReceipt.append("\t"+no+"\tTussidex Forte\t\t       "+ Tussidex+"\t\t"+df.format(newPriceTu)+"\n");
                    total = total + newPriceTu;
                }
                if(cbParacetamol.isSelected())
                {   
                    int Paracetamol = Integer.parseInt(tfParacetamol.getText());
                    no = no + 1;
                    double newPricePa =(priceParacetamol)*Paracetamol;
                    taReceipt.append("\t"+no+"\tParacetamol\t\t       "+ Paracetamol+"\t\t"+df.format(newPricePa)+"\n");
                    total = total + newPricePa;
                }
                if(cbDyrito.isSelected())
                {
                    int Dyrito = Integer.parseInt(tfDyrito.getText());
                    no = no + 1;
                    double newPriceDy = (priceDyrito)*Dyrito;
                    taReceipt.append("\t"+no+"\tDyrito Tablet\t\t       "+ Dyrito+"\t\t"+df.format(newPriceDy)+"\n");
                    total = total + newPriceDy;
                }
                if(cbZelox.isSelected())
                {   
                    int Zelox = Integer.parseInt(tfZelox.getText());
                    no = no + 1;
                    double newPriceZe =(priceZelox)*Zelox;
                    taReceipt.append("\t"+no+"\tZelox-II\t\t       "+ Zelox+"\t\t"+df.format(newPriceZe)+"\n");
                    total = total + newPriceZe;
                }
                if(cbMexomide.isSelected())
                {   
                    int Mexomide = Integer.parseInt(tfMexomide.getText());
                    no = no + 1;
                    double newPriceMe =(priceMexomide)*Mexomide;
                    taReceipt.append("\t"+no+"\tMexomide Tablet\t       "+ Mexomide+"\t\t"+df.format(newPriceMe)+"\n");
                    total = total + newPriceMe;
                }
                if(cbHyomide.isSelected())
                {   
                    int Hyomide = Integer.parseInt(tfHyomide.getText());
                    no = no + 1;
                    double newPriceHy =(priceHyomide)*Hyomide;
                    taReceipt.append("\t"+no+"\tHyomide Tablet\t\t       "+ Hyomide+"\t\t"+df.format(newPriceHy)+"\n");
                    total = total + newPriceHy;
                }
                if(cbNazin.isSelected())
                {   
                    int Nazin = Integer.parseInt(tfNazin.getText());
                    no = no + 1;
                    double newPriceNa =(priceNazin)*Nazin;
                    taReceipt.append("\t"+no+"\tNazin Tablet\t\t       "+ Nazin+"\t\t"+df.format(newPriceNa)+"\n");
                    total = total + newPriceNa;
                }
                if(cbUphalyte.isSelected())
                {   
                    int Uphalyte = Integer.parseInt(tfUphalyte.getText());
                    no = no + 1;
                    double newPriceUp =(priceUphalyte)*Uphalyte;
                    taReceipt.append("\t"+no+"\tUphalyte Orange\t       "+ Uphalyte+"\t\t"+df.format(newPriceUp)+"\n");
                    total = total + newPriceUp;
                }
                if(cbOriginal.isSelected())
                {   
                    int Original = Integer.parseInt(tfOriginal.getText());
                    no = no + 1;
                    double newPriceOr =(priceOriginal)*Original;
                    taReceipt.append("\t"+no+"\tUphalyte Original\t       "+ Original+"\t\t"+df.format(newPriceOr)+"\n");
                    total = total + newPriceOr;
                }
                if(cb1.isSelected())
                {   
                    int n1 = Integer.parseInt(tf1.getText());
                    no = no + 1;
                    double newPrice1 =(price1)*n1;
                    taReceipt.append("\t"+no+"\tAbacavir Sulfate\t\t       "+ n1+"\t\t"+df.format(newPrice1)+"\n");
                    total = total + newPrice1;
                }
                if(cb2.isSelected())
                {   
                    int n2 = Integer.parseInt(tf2.getText());
                    no = no + 1;
                    double newPrice2 =(price2)*n2;
                    taReceipt.append("\t"+no+"\tBionect Cream, Gel\t       "+ n2+"\t\t"+df.format(newPrice2)+"\n");
                    total = total + newPrice2;
                }
                if(cb3.isSelected())
                {   
                    int n3 = Integer.parseInt(tf3.getText());
                    no = no + 1;
                    double newPrice3 =(price3)*n3;
                    taReceipt.append("\t"+no+"\tCytogam\t\t       "+ n3+"\t\t"+df.format(newPrice3)+"\n");
                    total = total + newPrice3;
                }
                if(cb4.isSelected())
                {   
                    int n4 = Integer.parseInt(tf4.getText());
                    no = no + 1;
                    double newPrice4 =(price4)*n4;
                    taReceipt.append("\t"+no+"\tDarvon Compound\t       "+ n4+"\t\t"+df.format(newPrice4)+"\n");
                    total = total + newPrice4;
                }
                if(cb5.isSelected())
                {   
                    int n5 = Integer.parseInt(tf5.getText());
                    no = no + 1;
                    double newPrice5 =(price5)*n5;
                    taReceipt.append("\t"+no+"\tEurax\t\t       "+ n5+"\t\t"+df.format(newPrice5)+"\n");
                    total = total + newPrice5;
                }
                if(cb6.isSelected())
                {   
                    int n6 = Integer.parseInt(tf6.getText());
                    no = no + 1;
                    double newPrice6 =(price6)*n6;
                    taReceipt.append("\t"+no+"\tFortesta\t\t       "+ n6+"\t\t"+df.format(newPrice6)+"\n");
                    total = total + newPrice6;
                }
                if(cb7.isSelected())
                {   
                    int n7 = Integer.parseInt(tf7.getText());
                    no = no + 1;
                    double newPrice7 =(price7)*n7;
                    taReceipt.append("\t"+no+"\tOxsoralen-Ultra\t\t       "+ n7+"\t\t"+df.format(newPrice7)+"\n");
                    total = total + newPrice7;
                }
                if(cb8.isSelected())
                {   
                    int n8 = Integer.parseInt(tf8.getText());
                    no = no + 1;
                    double newPrice8 =(price8)*n8;
                    taReceipt.append("\t"+no+"\tSulfasalazine Tablet\t       "+ n8+"\t\t"+df.format(newPrice8)+"\n");
                    total = total + newPrice8;
                }
                if(cb9.isSelected())
                {   
                    int n9 = Integer.parseInt(tf9.getText());
                    no = no + 1;
                    double newPrice9 =(price9)*n9;
                    taReceipt.append("\t"+no+"\tYellow Fever Vaccine\t       "+ n9+"\t\t"+df.format(newPrice9)+"\n");
                    total = total + newPrice9;
                }
                if(cb10.isSelected())
                {   
                    int n10 = Integer.parseInt(tf10.getText());
                    no = no + 1;
                    double newPrice10 =(price10)*n10;
                    taReceipt.append("\t"+no+"\tLidocaine\t\t       "+ n10+"\t\t"+df.format(newPrice10)+"\n");
                    total = total + newPrice10;
                }
            }
            taReceipt.append("\n\t\t\t\t\t             Total        "+df.format(total));
            taReceipt.append("\n\t\t Thank you Come again ");
            taReceipt.append("\n\t\t May the force be with you");
                 
        }    
        //if click button Exit
        else if(e.getSource() == btnExit)
        {
            System.exit(-1);
        }
        else if(e.getSource() == btnExit2)
        {
            System.exit(-1);
        }
        else if(e.getSource() == btnClear2)
        {
            tfCashierName.setText("");
            tfIC.setText("");
            password.setText("");
        }
        else if(e.getSource() == btnLogOut)
        {
                panelMember.setEnabled(false);
        pCustom.setEnabled(false);
        panelButton.setEnabled(false);
        panelReceipt.setEnabled(false);
        rbMember.setEnabled(false);
        rbNonMember.setEnabled(false);
        cbBena.setEnabled(false);
        cbTussidex.setEnabled(false);
        cbParacetamol.setEnabled(false);
        cbDyrito.setEnabled(false);
        cbZelox.setEnabled(false);
        cbMexomide.setEnabled(false);
        cbHyomide.setEnabled(false);
        cbNazin.setEnabled(false);
        cbUphalyte.setEnabled(false);
        cbOriginal.setEnabled(false);
        cb1.setEnabled(false);
        cb2.setEnabled(false);
        cb3.setEnabled(false);
        cb4.setEnabled(false);
        cb5.setEnabled(false);
        cb6.setEnabled(false);
        cb7.setEnabled(false);
        cb8.setEnabled(false);
        cb9.setEnabled(false);
        cb10.setEnabled(false);
        tfBena.setEnabled(false);
        tfTussidex.setEnabled(false);
        tfParacetamol.setEnabled(false);
        tfDyrito.setEnabled(false);
        tfZelox.setEnabled(false);
        tfMexomide.setEnabled(false);
        tfHyomide.setEnabled(false);
        tfNazin.setEnabled(false);
        tfUphalyte.setEnabled(false);
        tfOriginal.setEnabled(false);
        tf1.setEnabled(false);
        tf2.setEnabled(false);
        tf3.setEnabled(false);
        tf4.setEnabled(false);
        tf5.setEnabled(false);
        tf6.setEnabled(false);
        tf7.setEnabled(false);
        tf8.setEnabled(false);
        tf9.setEnabled(false);
        tf10.setEnabled(false);
        btnOk.setEnabled(false);
        btnClear.setEnabled(false);
        btnExit.setEnabled(false);
        taReceipt.setEnabled(false);
        
        
        
        
        
        
        
        taReceipt.setText("");
            cbBena.setSelected(false);
            cbTussidex.setSelected(false);
            cbParacetamol.setSelected(false);
            cbDyrito.setSelected(false);
            cbZelox.setSelected(false);
            cbMexomide.setSelected(false);
            cbHyomide.setSelected(false);
            cbNazin.setSelected(false);
            cbUphalyte.setSelected(false);
            cbOriginal.setSelected(false);
            cb1.setSelected(false);
            cb2.setSelected(false);
            cb3.setSelected(false);
            cb4.setSelected(false);
            cb5.setSelected(false);
            cb6.setSelected(false);
            cb7.setSelected(false);
            cb8.setSelected(false);
            cb9.setSelected(false);
            cb10.setSelected(false);
            tfBena.setText("*");
            tfTussidex.setText("*");
            tfDyrito.setText("*");
            tfParacetamol.setText("*");
            tfZelox.setText("*");
            tfMexomide.setText("*");
            tfHyomide.setText("*");
            tfNazin.setText("*");
            tfUphalyte.setText("*");
            tfOriginal.setText("*");
            tf1.setText("*");
            tf2.setText("*");
            tf3.setText("*");
            tf4.setText("*");
            tf5.setText("*");
            tf6.setText("*");
            tf7.setText("*");
            tf8.setText("*");
            tf9.setText("*");
            tf10.setText("*");
            rbMember.setSelected(false);
            rbNonMember.setSelected(false);
        }
        else if(e.getSource() == btnSubmit)
        {
            if(! tfCashierName.getText().equals(""))
            {
                if(! tfIC.getText().equals(""))
                {
                    if(! password.getText().equals(""))
                    {
                    
                     panelMember.setEnabled(true);
                        pCustom.setEnabled(true);
                        panelButton.setEnabled(true);
                        panelReceipt.setEnabled(true);
                        rbMember.setEnabled(true);
                        rbNonMember.setEnabled(true);
                        cbBena.setEnabled(true);
                        cbTussidex.setEnabled(true);
                        cbParacetamol.setEnabled(true);
                        cbDyrito.setEnabled(true);
                        cbZelox.setEnabled(true);
                        cbMexomide.setEnabled(true);
                        cbHyomide.setEnabled(true);
                        cbNazin.setEnabled(true);
                        cbUphalyte.setEnabled(true);
                        cbOriginal.setEnabled(true);
                        cb1.setEnabled(true);
                        cb2.setEnabled(true);
                        cb3.setEnabled(true);
                        cb4.setEnabled(true);
                        cb5.setEnabled(true);
                        cb6.setEnabled(true);
                        cb7.setEnabled(true);
                        cb8.setEnabled(true);
                        cb9.setEnabled(true);
                        cb10.setEnabled(true);
                        tfBena.setEnabled(true);
                        tfTussidex.setEnabled(true);
                        tfParacetamol.setEnabled(true);
                        tfDyrito.setEnabled(true);
                        tfZelox.setEnabled(true);
                        tfMexomide.setEnabled(true);
                        tfHyomide.setEnabled(true);
                        tfNazin.setEnabled(true);
                        tfUphalyte.setEnabled(true);
                        tfOriginal.setEnabled(true);
                        tf1.setEnabled(true);
                        tf2.setEnabled(true);
                        tf3.setEnabled(true);
                        tf4.setEnabled(true);
                        tf5.setEnabled(true);
                        tf6.setEnabled(true);
                        tf7.setEnabled(true);
                        tf8.setEnabled(true);
                        tf9.setEnabled(true);
                        tf10.setEnabled(true);
                        btnOk.setEnabled(true);
                        btnClear.setEnabled(true);
                        btnExit.setEnabled(true);
                        taReceipt.setEnabled(true);
                    }
                    else{JOptionPane.showMessageDialog(null,"Please Enter Password");
                        
                    }
                    
                }
                else{
                       JOptionPane.showMessageDialog(null,"Please Enter IC Number");
                    }
              
                
            }
            else{
                JOptionPane.showMessageDialog(null,"Please Enter Name");
            }
        
        
    
               
                
                
            
        }
        //if click button Clear
        else if(e.getSource() == btnClear)
        {
            taReceipt.setText("");
            cbBena.setSelected(false);
            cbTussidex.setSelected(false);
            cbParacetamol.setSelected(false);
            cbDyrito.setSelected(false);
            cbZelox.setSelected(false);
            cbMexomide.setSelected(false);
            cbHyomide.setSelected(false);
            cbNazin.setSelected(false);
            cbUphalyte.setSelected(false);
            cbOriginal.setSelected(false);
            cb1.setSelected(false);
            cb2.setSelected(false);
            cb3.setSelected(false);
            cb4.setSelected(false);
            cb5.setSelected(false);
            cb6.setSelected(false);
            cb7.setSelected(false);
            cb8.setSelected(false);
            cb9.setSelected(false);
            cb10.setSelected(false);
            tfBena.setText("*");
            tfTussidex.setText("*");
            tfDyrito.setText("*");
            tfParacetamol.setText("*");
            tfZelox.setText("*");
            tfMexomide.setText("*");
            tfHyomide.setText("*");
            tfNazin.setText("*");
            tfUphalyte.setText("*");
            tfOriginal.setText("*");
            tf1.setText("*");
            tf2.setText("*");
            tf3.setText("*");
            tf4.setText("*");
            tf5.setText("*");
            tf6.setText("*");
            tf7.setText("*");
            tf8.setText("*");
            tf9.setText("*");
            tf10.setText("*");
            rbMember.setSelected(false);
            rbNonMember.setSelected(false);
            
        }
        else{
            Object source = e.getSource();
            JMenuItem selection = (JMenuItem)source;
            String cmd = selection.getText();
            
            if(cmd.equals("Exit"))
                System.exit(-1);
        }
        
    }
}