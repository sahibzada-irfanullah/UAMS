
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.border.*;
import java.text.NumberFormat; 

public class MUam {

 
 public static void main(String[] args) {
  StartSplashScreen startsplash = new StartSplashScreen(3000);
     startsplash.showSplashAndExit(); 
  Uam obg=new Uam(); 
 }

}

class Uam{
  JFrame frame;
  short iLab=1;
  JPanel labPanel,txPanel,rBPanel,labTxPanel,proPanel,ansPanel,labAnsPanel,labTxrBAnsProPanel,butPanel;
  Box ansProPanel;
  JButton calculate,reset,exit;
  Container c;
  JRadioButton viMs,viKmh,viKms,vfMs,vfKmh,vfKms,aMss,aKmss,aKmhh,tS,tH,tD,sM,sKm,sMil
    ,vfReq,viReq,aReq,tReq,sReq;
  JTextArea tAns,tPro;
  ButtonGroup bGVi,bGVf,bGT,bGS,bGA;
  JTextField txVf,txVi,txA,txS,txT;
  JLabel lVf,lVi,lA,lS,lT,lLab;
  String viUnit="nounit",vfUnit="nounit",aUnit="nounit",sUnit="nounit",tUnit="nounit";
  double vf,vi,a,t,s;
  public void initGUI(){
  frame=new JFrame();
   frame.setTitle("Uniform Accelarated Motion V 1.0 ");
  c=new Container();
  c=frame.getContentPane();
  c.setLayout(new BorderLayout());
  lVf=new JLabel("     Fianl Velocity (vf)=");
  lVi=new JLabel("    Initial Velocity(vi)=");
  lA=new JLabel("    Accelaration (a)=");
  lS=new JLabel("    Distance (s)=");
  lT=new JLabel("    Time (t)=");
  txVf=new JTextField(8);
  txVi=new JTextField(8);
  txA=new JTextField(8);
  txS=new JTextField(8);
  txT=new JTextField(8);
  Border lBevelBorder=BorderFactory.createLoweredBevelBorder();
  txVi.setBorder(lBevelBorder);
  txVf.setBorder(lBevelBorder);
  txA.setBorder(lBevelBorder);
  txS.setBorder(lBevelBorder);
  txT.setBorder(lBevelBorder);
  labPanel=new JPanel();
  labPanel.setLayout(new GridLayout(5,1));
  txPanel=new JPanel(new GridLayout(5,1));
 labPanel.add(lVi);
  txPanel.add(txVi);
  labPanel.add(lVf);
  txPanel.add(txVf);
  labPanel.add(lT);
  txPanel.add(txT);
  labPanel.add(lA);
  txPanel.add(txA);
  labPanel.add(lS);
  txPanel.add(txS);
  viMs=new JRadioButton("m/s",false);
  viKmh=new JRadioButton("km/h",false);
  viKms=new JRadioButton("km/s",false);
  viReq=new JRadioButton("Required?",false);
  
    vfMs=new JRadioButton("m/s",false);
  vfKms=new JRadioButton("km/s",false);
  vfKmh=new JRadioButton("km/h",false);
  vfReq=new JRadioButton("Required?",false);
  
    aMss=new JRadioButton("m/ss",false);
  aKmss=new JRadioButton("km/ss",false);
  aKmhh=new JRadioButton("km/hh",false);
  aReq=new JRadioButton("Required?",false);
  
    tS=new JRadioButton("s",false);
  tH=new JRadioButton("h",false);
  tD=new JRadioButton("day(s)",false);
  tReq=new JRadioButton("Required?",false);
  
    sM=new JRadioButton("m",false);
  sKm=new JRadioButton("km",false);
  sMil=new JRadioButton("mile(s)",false);
  sReq=new JRadioButton("Required?",false);
  
  bGVf=new ButtonGroup();
  bGT=new ButtonGroup();
  bGS=new ButtonGroup();
  bGA=new ButtonGroup();
  bGVi=new ButtonGroup();
   viKms.setEnabled(false);             //Disalbing the radio buttons.................
  viKmh.setEnabled(false);              //Disalbing the radio buttons.................
  vfKms.setEnabled(false);                //Disalbing the radio buttons.................
  vfKmh.setEnabled(false);              //Disalbing the radio buttons.................
  aKmss.setEnabled(false);             //Disalbing the radio buttons.................
  aKmhh.setEnabled(false);               //Disalbing the radio buttons.................
  tH.setEnabled(false);              //Disalbing the radio buttons.................
  tD.setEnabled(false);                //Disalbing the radio buttons.................
  sKm.setEnabled(false);             //Disalbing the radio buttons.................
  sMil.setEnabled(false);            //Disalbing the radio buttons.................
                                   //txVf,txVi,txA,txS,txT  registration with keychecking class
  KeyChecking kc=new  KeyChecking();
  txVf.addKeyListener(kc);    //  registration with keychecking 
  txVi.addKeyListener(kc);         //  registration with keychecking 
  txA.addKeyListener(kc);        //  registration with keychecking 
  txS.addKeyListener(kc);         //  registration with keychecking 
  txT.addKeyListener(kc);            //  registration with keychecking 
  bGVi.add(viMs);
  bGVi.add(viKmh);
  bGVi.add(viKms);
  bGVi.add(viReq);
  
  bGVf.add(vfMs);
  bGVf.add(vfKms);
  bGVf.add(vfKmh);
  bGVf.add(vfReq);
  
   bGT.add(tS);
  bGT.add(tH);
  bGT.add(tD);
  bGT.add(tReq);
  
   bGA.add(aMss);
  bGA.add(aKmhh);
  bGA.add(aKmss);
  bGA.add(aReq);
  
  bGS.add(sM);
  bGS.add(sKm);
  bGS.add(sMil);
  bGS.add(sReq);
  
 
 
  rBPanel=new JPanel(new GridLayout(5,4));
  rBPanel.add(viMs);
  rBPanel.add(viKms);
  rBPanel.add(viKmh);
  rBPanel.add(viReq);
  
  rBPanel.add(vfMs);
  rBPanel.add(vfKms);
  rBPanel.add(vfKmh);
  rBPanel.add(vfReq);
  
    rBPanel.add(tS);
  rBPanel.add(tH);
  rBPanel.add(tD);
  rBPanel.add(tReq);
  
  rBPanel.add(aMss);
  rBPanel.add(aKmss);
  rBPanel.add(aKmhh);
  rBPanel.add(aReq);
  
  rBPanel.add(sM);
  rBPanel.add(sKm);
  rBPanel.add(sMil);
  rBPanel.add(sReq);
  
  rBItemListener rBHandler=new rBItemListener();
  viMs.addItemListener(rBHandler);
  viKmh.addItemListener(rBHandler);
  viKms.addItemListener(rBHandler);
  viReq.addItemListener(rBHandler);
  
  vfMs.addItemListener(rBHandler);
  vfKms.addItemListener(rBHandler);
  vfKmh.addItemListener(rBHandler);
  vfReq.addItemListener(rBHandler);
  
  tS.addItemListener(rBHandler);
  tH.addItemListener(rBHandler);
  tD.addItemListener(rBHandler);
  tReq.addItemListener(rBHandler);
  
  aMss.addItemListener(rBHandler);
  aKmhh.addItemListener(rBHandler);
  aKmss.addItemListener(rBHandler);
  aReq.addItemListener(rBHandler);
  
  sM.addItemListener(rBHandler);
  sKm.addItemListener(rBHandler);
  sMil.addItemListener(rBHandler);
  sReq.addItemListener(rBHandler);
  
  labTxPanel=new JPanel(new GridLayout(1,2));
  labTxPanel.add(labPanel);
  labTxPanel.add(txPanel);
  ansPanel=new JPanel(new FlowLayout());
  proPanel=new JPanel(new FlowLayout());
  ansProPanel= Box.createHorizontalBox();
  tAns=new JTextArea(3,15);
  tPro=new JTextArea(3,25);
  Color c1=new Color(223,255,242);
  Color c2=new Color(221,226,248);
  tAns.setBackground(c1);
  tPro.setBackground(c2);
  tAns.setBorder(new BevelBorder(BevelBorder.RAISED));
tPro.setBorder(new BevelBorder(BevelBorder.LOWERED));
reset=new JButton("Reset");
  calculate=new JButton("Calculate");
  exit=new JButton("Exit");
  
  butPanel=new JPanel(new GridLayout(3,1,0,3));
 butPanel.add(calculate);
  butPanel.add(reset);
  butPanel.add(exit);
  tAns.setText("Answer will display here");
  tPro.setText("procedure with basic formulae and \nderived formaulae\nwill display \n\n\n\n ");
  ansPanel.add(tAns);
  ansPanel.add(new JScrollPane(tPro));
  ansPanel.add(butPanel);
  ansProPanel.add(ansPanel);
  ansProPanel.add(proPanel);
  labTxrBAnsProPanel=new JPanel(new BorderLayout(2,1));
  labTxrBAnsProPanel.add(labTxPanel,BorderLayout.WEST);
  labTxrBAnsProPanel.add(rBPanel,BorderLayout.CENTER);
  labTxrBAnsProPanel.add(ansProPanel,BorderLayout.SOUTH);
  c.add(labTxrBAnsProPanel,BorderLayout.CENTER);
  lLab=new JLabel(" ");//1 space
  frame.setVisible(true);
  frame.setSize(660,300);
  frame.setResizable(false);
  butActionListener butHandler=new butActionListener();
  calculate.addActionListener(butHandler);
  exit.addActionListener(butHandler);
  reset.addActionListener(butHandler);
  
    ansProPanel.setBorder(new TitledBorder(new LineBorder(Color.black, 1),
                        "Answer(s)---------------------------------Procedure"));//border
    labTxPanel.setBorder(new SoftBevelBorder(SoftBevelBorder.RAISED));//border
rBPanel.setBorder(new SoftBevelBorder(SoftBevelBorder.LOWERED));//border
  frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
  
  Timer t=new Timer(100,new labAnim());
 t.start();
 
 }
  private class labAnim implements ActionListener{
  
    public void actionPerformed(ActionEvent ae){
      if(iLab==1)
      {
        lLab.setFont(new Font("Serif",Font.BOLD+Font.ITALIC,13));
 if(lLab.getText()==" ")//1 space
    {
   
    lLab.setText("D");
    c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="D")
    {
    lLab.setText("De");
      c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="De")
    {
      lLab.setText("Dev");
    c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="Dev")
    {
      lLab.setText("Deve");
    c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="Deve")
    {
      lLab.setText("Devel");
    c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="Devel")
    {
      lLab.setText("Develo");
    c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="Develo")
    {
      lLab.setText("Develop");
    c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="Develop")
    {
      lLab.setText("Develope");
    c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="Develope")
    {
      lLab.setText("Developed");
    c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="Develope")
    {
      lLab.setText("Developed");
    c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="Developed")
    {
      lLab.setText("Developed ");
    c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="Developed ")
    {
      lLab.setText("Developed b");
    c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="Developed b")
    {
      lLab.setText("Developed by");
    c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="Developed by")
    {
      lLab.setText("Developed by ");
    c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="Developed by ")
    {
      lLab.setText("Developed by S");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Developed by S")
    {
      lLab.setText("Developed by Sa");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Developed by Sa")
    {
      lLab.setText("Developed by Sah");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Developed by Sah")
    {
      lLab.setText("Developed by Sahi");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Developed by Sahi")
    {
      lLab.setText("Developed by Sahib");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Developed by Sahib")
    {
      lLab.setText("Developed by Sahibz");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Developed by Sahibz")
    {
      lLab.setText("Developed by Sahibza");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Developed by Sahibza")
    {
      lLab.setText("Developed by Sahibzad");
    c.add(lLab,BorderLayout.SOUTH);

    }
else if(lLab.getText()=="Developed by Sahibzad")
    {
      lLab.setText("Developed by Sahibzada");
    c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="Developed by Sahibzada")
    {
      lLab.setText("Developed by Sahibzada I");
    c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="Developed by Sahibzada I")
    {
      lLab.setText("Developed by Sahibzada Ir");
    c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="Developed by Sahibzada Ir")
    {
      lLab.setText("Developed by Sahibzada Irf");
    c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="Developed by Sahibzada Irf")
    {
      lLab.setText("Developed by Sahibzada Irfa");
    c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="Developed by Sahibzada Irfa")
    {
      lLab.setText("Developed by Sahibzada Irfan");
    c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="Developed by Sahibzada Irfan")
    {
      lLab.setText("Developed by Sahibzada Irfanu");
    c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="Developed by Sahibzada Irfanu")
    {
      lLab.setText("Developed by Sahibzada Irfanul");
    c.add(lLab,BorderLayout.SOUTH);
    }else if(lLab.getText()=="Developed by Sahibzada Irfanul")
    {
      lLab.setText("Developed by Sahibzada Irfanull");
    c.add(lLab,BorderLayout.SOUTH);
    }else if(lLab.getText()=="Developed by Sahibzada Irfanull")
    {
      lLab.setText("Developed by Sahibzada Irfanulla");
    c.add(lLab,BorderLayout.SOUTH);
    }
    else if(lLab.getText()=="Developed by Sahibzada Irfanulla")
    {
      lLab.setText("Developed by Sahibzada Irfanullah");
    c.add(lLab,BorderLayout.SOUTH);
    } else if(lLab.getText()=="Developed by Sahibzada Irfanullah")
    {
      lLab.setText("Developed by Sahibzada Irfanullah.");
    c.add(lLab,BorderLayout.SOUTH);
    }
     else if(lLab.getText()=="Developed by Sahibzada Irfanullah.")
    {
      lLab.setText("Developed by Sahibzada Irfanullah. ");
    c.add(lLab,BorderLayout.SOUTH);
    }
  else if(lLab.getText()=="Developed by Sahibzada Irfanullah. ")
    {
      lLab.setText("Developed by Sahibzada Irfanullah.  ");
    c.add(lLab,BorderLayout.SOUTH);
    }
  else if(lLab.getText()=="Developed by Sahibzada Irfanullah.  ")
    {
      lLab.setText("  ");//2 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
  else if(lLab.getText()=="  ")//2 spaces
    {
      lLab.setText("   ");//3 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="   ")//3 spaces
    {
  lLab.setForeground(Color.BLUE);
      lLab.setText("Developed by Sahibzada Irfanullah.   ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Developed by Sahibzada Irfanullah.   ")
    {
      lLab.setText("Developed by Sahibzada Irfanullah.    ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Developed by Sahibzada Irfanullah.    ")
    {
      lLab.setText("Developed by Sahibzada Irfanullah.     ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Developed by Sahibzada Irfanullah.     ")
    {
      lLab.setText("Developed by Sahibzada Irfanullah.      ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Developed by Sahibzada Irfanullah.      ")
    {
      lLab.setText("    ");//4 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="    ")//4 spaces
    {
      lLab.setText("     ");//5 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="     ")//5 spaces
    {
  lLab.setForeground(Color.RED);
      lLab.setText("Developed by Sahibzada Irfanullah.       ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Developed by Sahibzada Irfanullah.       ")
    {
      lLab.setText("Developed by Sahibzada Irfanullah.        ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Developed by Sahibzada Irfanullah.        ")
    {
      lLab.setText("Developed by Sahibzada Irfanullah.         ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Developed by Sahibzada Irfanullah.         ")
    {
      lLab.setText("Developed by Sahibzada Irfanullah.          ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Developed by Sahibzada Irfanullah.          ")
    {
      lLab.setText("Developed by Sahibzada Irfanullah.           ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Developed by Sahibzada Irfanullah.           ")
    {
      lLab.setText("      ");//6 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="      ")//6 spaces
    {
      lLab.setText("       ");//7 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="       ")//7 spaces
    {
  lLab.setForeground(Color.MAGENTA);
      lLab.setText("Developed by Sahibzada Irfanullah.            ");
    c.add(lLab,BorderLayout.SOUTH);
    
   
}else if(lLab.getText()=="Developed by Sahibzada Irfanullah.            ")
    {
      lLab.setText("        ");//8 spaces
    c.add(lLab,BorderLayout.SOUTH);
    iLab=2;
}
    }//End Name
     else if(iLab==2)
      {lLab.setForeground(Color.BLACK);
    
    if(lLab.getText()=="        ")
    {
      lLab.setText("B");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="B")
    {
      lLab.setText("BS");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS")
    {
      lLab.setText("BS(");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(")
    {
      lLab.setText("BS(C");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(C")
    {
      lLab.setText("BS(CS");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS")
    {
      lLab.setText("BS(CS)");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS)")
    {
      lLab.setText("BS(CS) ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) ")
    {
      lLab.setText("BS(CS) 5");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5")
    {
      lLab.setText("BS(CS) 5t");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5t")
    {
      lLab.setText("BS(CS) 5th");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th")
    {
      lLab.setText("BS(CS) 5th ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th ")
    {
      lLab.setText("BS(CS) 5th T");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th T")
    {
      lLab.setText("BS(CS) 5th Te");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Te")
    {
      lLab.setText("BS(CS) 5th Ter");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Ter")
    {
      lLab.setText("BS(CS) 5th Term");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term")
    {
      lLab.setText("BS(CS) 5th Term,");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term,")
    {
      lLab.setText("BS(CS) 5th Term, ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, ")
    {
      lLab.setText("BS(CS) 5th Term, G");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, G")
    {
      lLab.setText("BS(CS) 5th Term, Go");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Go")
    {
      lLab.setText("BS(CS) 5th Term, Gom");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gom")
    {
      lLab.setText("BS(CS) 5th Term, Goma");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Goma")
    {
      lLab.setText("BS(CS) 5th Term, Gomal");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal")
    {
      lLab.setText("BS(CS) 5th Term, Gomal ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal ")
    {
      lLab.setText("BS(CS) 5th Term, Gomal U");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal U")
    {
      lLab.setText("BS(CS) 5th Term, Gomal Un");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal Un")
    {
      lLab.setText("BS(CS) 5th Term, Gomal Uni");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal Uni")
    {
      lLab.setText("BS(CS) 5th Term, Gomal Univ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal Univ")
    {
      lLab.setText("BS(CS) 5th Term, Gomal Unive");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal Unive")
    {
      lLab.setText("BS(CS) 5th Term, Gomal Univer");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal Univer")
    {
      lLab.setText("BS(CS) 5th Term, Gomal Univers");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal Univers")
    {
      lLab.setText("BS(CS) 5th Term, Gomal Universi");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal Universi")
    {
      lLab.setText("BS(CS) 5th Term, Gomal Universit");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal Universit")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University ");
    c.add(lLab,BorderLayout.SOUTH);
    }

else if(lLab.getText()=="BS(CS) 5th Term, Gomal University ")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I.");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I.")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. ")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. K");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. K")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Kh");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Kh")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Kha");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Kha")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan,");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan,")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, ")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, K");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, K")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KP");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KP")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK,");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK,")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, ")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, P");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, P")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pa");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pa")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pak");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pak")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Paki");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Paki")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakis");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakis")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakist");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakist")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakista");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakista")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan. ");
    c.add(lLab,BorderLayout.SOUTH);
    }

else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan. ")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.  ");
    c.add(lLab,BorderLayout.SOUTH);
    }

else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.  ")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.   ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.   ")
    {
      lLab.setText("  ");//2 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
  else if(lLab.getText()=="  ")//2 spaces
    {
      lLab.setText("   ");//3 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="   ")//3 spaces
   {
  lLab.setForeground(Color.MAGENTA);

      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.    ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.    ")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.     ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.     ")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.      ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.      ")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.       ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.       ")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.        ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.        ")
    {
      lLab.setText("    ");//4 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="    ")//4 spaces
    {
      lLab.setText("     ");//5 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="     ")//5 spaces
    {lLab.setForeground(Color.RED);
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.         ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.         ")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.          ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.          ")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.           ");
    c.add(lLab,BorderLayout.SOUTH);
     }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.           ")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.            ");//12 spaces
    c.add(lLab,BorderLayout.SOUTH);
     }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.            ")
    {
      lLab.setText("      ");//6 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
        else if(lLab.getText()=="      ")//6 spaces
    {
      lLab.setText("       ");//7 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="       ")//7 spaces
    {lLab.setForeground(Color.BLUE);
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.             ");//13 spaces
    c.add(lLab,BorderLayout.SOUTH);
     }
else if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.             ")
    {
      lLab.setText("BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.              ");//14 spaces
    c.add(lLab,BorderLayout.SOUTH);
   iLab=3;  
}
     }//End Address
     else if(iLab==3)
{
if(lLab.getText()=="BS(CS) 5th Term, Gomal University D.I. Khan, KPK, Pakistan.              ")//14 spaces
    {lLab.setForeground(Color.BLACK);
      lLab.setText("E");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="E")
    {
      lLab.setText("Em");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Em")
    {
      lLab.setText("Ema");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Ema")
    {
      lLab.setText("Emai");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Emai")
    {
      lLab.setText("Email");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email")
    {
      lLab.setText("Email:");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email:")
    {
      lLab.setText("Email: ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: ")
    {
      lLab.setText("Email: i");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: i")
    {
      lLab.setText("Email: ir");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: ir")
    {
      lLab.setText("Email: irf");
    c.add(lLab,BorderLayout.SOUTH);
    }

else if(lLab.getText()=="Email: irf")
    {
      lLab.setText("Email: irfa");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfa")
    {
      lLab.setText("Email: irfan");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan")
    {
      lLab.setText("Email: irfan.");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.")
    {
      lLab.setText("Email: irfan.g");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.")
    {
      lLab.setText("Email: irfan.g");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.")
    {
      lLab.setText("Email: irfan.g");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.")
    {
      lLab.setText("Email: irfan.g");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.g")
    {
      lLab.setText("Email: irfan.go");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.go")
    {
      lLab.setText("Email: irfan.gom");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gom")
    {
      lLab.setText("Email: irfan.goma");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.goma")
    {
      lLab.setText("Email: irfan.gomal");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gomal")
    {
      lLab.setText("Email: irfan.gomali");
    c.add(lLab,BorderLayout.SOUTH);
    }

else if(lLab.getText()=="Email: irfan.gomali")
    {
      lLab.setText("Email: irfan.gomalia");
    c.add(lLab,BorderLayout.SOUTH);
    }

else if(lLab.getText()=="Email: irfan.gomalia")
    {
      lLab.setText("Email: irfan.gomalian");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gomalian")
    {
      lLab.setText("Email: irfan.gomalian@");
    c.add(lLab,BorderLayout.SOUTH);
    }

else if(lLab.getText()=="Email: irfan.gomalian@")
    {
      lLab.setText("Email: irfan.gomalian@g");
    c.add(lLab,BorderLayout.SOUTH);
    }

else if(lLab.getText()=="Email: irfan.gomalian@g")
    {
      lLab.setText("Email: irfan.gomalian@gm");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gomalian@gm")
    {
      lLab.setText("Email: irfan.gomalian@gma");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gomalian@gma")
    {
      lLab.setText("Email: irfan.gomalian@gmai");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gomalian@gmai")
    {
      lLab.setText("Email: irfan.gomalian@gmail");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gomalian@gmail")
    {
      lLab.setText("Email: irfan.gomalian@gmail.");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gomalian@gmail.")
    {
      lLab.setText("Email: irfan.gomalian@gmail.c");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gomalian@gmail.c")
    {
      lLab.setText("Email: irfan.gomalian@gmail.co");
    c.add(lLab,BorderLayout.SOUTH);
    }

else if(lLab.getText()=="Email: irfan.gomalian@gmail.co")
    {
      lLab.setText("Email: irfan.gomalian@gmail.com");
    c.add(lLab,BorderLayout.SOUTH);
    }

else if(lLab.getText()=="Email: irfan.gomalian@gmail.com")
    {
      lLab.setText("Email: irfan.gomalian@gmail.com.");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gomalian@gmail.com.")
    {
      lLab.setText("Email: irfan.gomalian@gmail.com. ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gomalian@gmail.com. ")
    {
      lLab.setText("Email: irfan.gomalian@gmail.com.  ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gomalian@gmail.com.  ")
    {
      lLab.setText("Email: irfan.gomalian@gmail.com.   ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gomalian@gmail.com.   ")
    {
      lLab.setText("  ");//2 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
  else if(lLab.getText()=="  ")//2 spaces
    {
      lLab.setText("   ");//3 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="   ")//3 spaces
    {
  lLab.setForeground(Color.BLUE);
      lLab.setText("Email: irfan.gomalian@gmail.com.    ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gomalian@gmail.com.    ")
    {
      lLab.setText("Email: irfan.gomalian@gmail.com.     ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gomalian@gmail.com.     ")
    {
      lLab.setText("Email: irfan.gomalian@gmail.com.      ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gomalian@gmail.com.     ")
    {
      lLab.setText("Email: irfan.gomalian@gmail.com.      ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gomalian@gmail.com.      ")
    {
      lLab.setText("    ");//4 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="    ")//4 spaces
    {
      lLab.setText("     ");//5 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="     ")//5 spaces
    {
  lLab.setForeground(Color.RED);
      lLab.setText("Email: irfan.gomalian@gmail.com.       ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gomalian@gmail.com.       ")
    {
      lLab.setText("Email: irfan.gomalian@gmail.com.        ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gomalian@gmail.com.        ")
    {
      lLab.setText("Email: irfan.gomalian@gmail.com.         ");
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gomalian@gmail.com.         ")
    {
      lLab.setText("Email: irfan.gomalian@gmail.com.          ");//11 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gomalian@gmail.com.          ")
    {
      lLab.setText("Email: irfan.gomalian@gmail.com.           ");//12 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="Email: irfan.gomalian@gmail.com.           ")
    {
      lLab.setText("      ");//6 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
        else if(lLab.getText()=="      ")//6 spaces
    {
      lLab.setText("       ");//7 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="       ")//7 spaces
    {
  lLab.setForeground(Color.MAGENTA);
      lLab.setText("Email: irfan.gomalian@gmail.com.            ");//13 spaces
    c.add(lLab,BorderLayout.SOUTH);
   iLab=4;
}


}
     else if(iLab==4)
     {

 if(lLab.getText()=="Email: irfan.gomalian@gmail.com.            ")
    {
   lLab.setForeground(Color.BLACK);
      lLab.setText("C");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="C")
    {
      lLab.setText("Ce");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Ce")
    {
      lLab.setText("Cel");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cel")
    {
      lLab.setText("Cell");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell")
    {
      lLab.setText("Cell#");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell#")
    {
      lLab.setText("Cell# ");
    c.add(lLab,BorderLayout.SOUTH);
}

else  if(lLab.getText()=="Cell# ")
    {
      lLab.setText("Cell# (");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (")
    {
      lLab.setText("Cell# (+");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+")
    {
      lLab.setText("Cell# (+9");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+9")
    {
      lLab.setText("Cell# (+92");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92")
    {
      lLab.setText("Cell# (+92)");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92)")
    {
      lLab.setText("Cell# (+92) ");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) ")
    {
      lLab.setText("Cell# (+92) 3");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 3")
    {
      lLab.setText("Cell# (+92) 31");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 31")
    {
      lLab.setText("Cell# (+92) 315");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 315")
    {
      lLab.setText("Cell# (+92) 315 ");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 315 ")
    {
      lLab.setText("Cell# (+92) 315 9");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 315 9")
    {
      lLab.setText("Cell# (+92) 315 98");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 315 98")
    {
      lLab.setText("Cell# (+92) 315 985");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 315 985")
    {
      lLab.setText("Cell# (+92) 315 985 ");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 315 985 ")
    {
      lLab.setText("Cell# (+92) 315 985 7");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 315 985 7")
    {
      lLab.setText("Cell# (+92) 315 985 70");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 315 985 70")
    {
      lLab.setText("Cell# (+92) 315 985 700");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 315 985 700")
    {
      lLab.setText("Cell# (+92) 315 985 7003");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 315 985 7003")
    {
      lLab.setText("Cell# (+92) 315 985 7003. ");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 315 985 7003. ")
    {
      lLab.setText("Cell# (+92) 315 985 7003.  ");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 315 985 7003.  ")
    {
      lLab.setText("Cell# (+92) 315 985 7003.   ");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 315 985 7003.   ")
    {
      lLab.setText("Cell# (+92) 315 985 7003.    ");
    c.add(lLab,BorderLayout.SOUTH);
}
else if(lLab.getText()=="Cell# (+92) 315 985 7003.    ")
    {
      lLab.setText("  ");//2 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
  else if(lLab.getText()=="  ")//2 spaces
    {
      lLab.setText("   ");//3 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="   ")//3 spaces
    {
  lLab.setForeground(Color.BLUE);
      lLab.setText("Cell# (+92) 315 985 7003.     ");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 315 985 7003.     ")
    {
      lLab.setText("Cell# (+92) 315 985 7003.      ");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 315 985 7003.      ")
    {
      lLab.setText("Cell# (+92) 315 985 7003.       ");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 315 985 7003.       ")
    {
      lLab.setText("Cell# (+92) 315 985 7003.        ");
    c.add(lLab,BorderLayout.SOUTH);
}
else if(lLab.getText()=="Cell# (+92) 315 985 7003.        ")
    {
      lLab.setText("    ");//4 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="    ")//4 spaces
    {
      lLab.setText("     ");//5 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="     ")//5 spaces
    {
  lLab.setForeground(Color.RED);
      lLab.setText("Cell# (+92) 315 985 7003.         ");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 315 985 7003.         ")
    {
      lLab.setText("Cell# (+92) 315 985 7003.          ");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 315 985 7003.          ")
    {
      lLab.setText("Cell# (+92) 315 985 7003.           ");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 315 985 7003.           ")
    {
      lLab.setText("Cell# (+92) 315 985 7003.            ");
    c.add(lLab,BorderLayout.SOUTH);
}
else if(lLab.getText()=="Cell# (+92) 315 985 7003.            ")
    {
      lLab.setText("      ");//6 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
        else if(lLab.getText()=="      ")//6 spaces
    {
      lLab.setText("       ");//7 spaces
    c.add(lLab,BorderLayout.SOUTH);
    }
else if(lLab.getText()=="       ")//7 spaces
    {
  lLab.setForeground(Color.MAGENTA);
      lLab.setText("Cell# (+92) 315 985 7003.             ");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 315 985 7003.             ")
    {
      lLab.setText("Cell# (+92) 315 985 7003.              ");
    c.add(lLab,BorderLayout.SOUTH);
}
else  if(lLab.getText()=="Cell# (+92) 315 985 7003.              ")
    {
      lLab.setText("Cell# (+92) 315 985 7003.               ");
    c.add(lLab,BorderLayout.SOUTH);
    lLab.setText(" ");//1 space
    iLab=1;
    lLab.setForeground(Color.BLACK);
}


}

    }//End actionPerformed method
  }//End LabAnimclass
  
  public class rBItemListener implements ItemListener{

public void itemStateChanged(ItemEvent ie){
  Color c3=new Color(238,238,238);
      if(ie.getSource()==viMs)
      {
       
        if(txVi.getText().equals("?"))
        {txVi.setText("");
         txVi.setBackground(Color.white);
        }
        viUnit="ms";
        txVi.setEditable(true);
        txVi.setBackground(Color.white);
      }
else  if(ie.getSource()==viKmh)
{
 
        if(txVi.getText().equals("?"))
  {txVi.setText("");
   txVi.setBackground(Color.white);
      }
  viUnit="kmh";
  txVi.setEditable(true);
  txVi.setBackground(Color.white);
} 
else if(ie.getSource()==viKms)
{
  
        if(txVi.getText().equals("?"))
  {txVi.setText("");
          txVi.setBackground(Color.white);
  }
viUnit="kms";
txVi.setEditable(true);
txVi.setBackground(Color.white);
}
else if(ie.getSource()==viReq)
{
  viUnit="?";
  txVi.setText(viUnit);
  txVi.setEditable(false);
txVi.setBackground(c3);
}
      
      if(ie.getSource()==vfMs)
      {
       if(txVf.getText().equals("?"))
  {txVf.setText("");
   txVf.setBackground(Color.white);
      }
vfUnit="ms";
 txVf.setEditable(true);
 txVf.setBackground(Color.white);
      }
else if(ie.getSource()==vfKmh)
{
  if(txVf.getText().equals("?"))
  {txVf.setText("");
   txVf.setBackground(Color.white);
      }
  vfUnit="kmh";
   txVf.setEditable(true);
    txVf.setBackground(Color.white);
}
else if(ie.getSource()==vfKms)
{
  if(txVf.getText().equals("?"))
  {txVf.setText("");
   txVf.setBackground(Color.white);
      }
  
vfUnit="kms";
 txVf.setEditable(true);
  txVf.setBackground(Color.white);
}
else if(ie.getSource()==vfReq)
{
  vfUnit="?";
  txVf.setEditable(false);
  txVf.setText(vfUnit);
  txVf.setBackground(c3);
}
      if(ie.getSource()==aMss)
      {
       if(txA.getText().equals("?"))
  {txA.setText("");
   txA.setBackground(Color.white);
      }    
aUnit="mss";
txA.setEditable(true);
 txA.setBackground(Color.white);
      }
else if(ie.getSource()==aKmss)
{
      
       if(txA.getText().equals("?"))
  {txA.setText("");
   txA.setBackground(Color.white);
      }
aUnit="kmss";
txA.setEditable(true);
txA.setBackground(Color.white);
}
else if(ie.getSource()==aKmhh)
{
       if(txA.getText().equals("?"))
  {txA.setText("");
   txA.setBackground(Color.white);
      }
aUnit="kmhh";
txA.setEditable(true);
txA.setBackground(Color.white);
}
else if(ie.getSource()==aReq)
{
  aUnit="?";
  txA.setEditable(false);
  txA.setText(aUnit);
  txA.setBackground(c3);
}

      if(ie.getSource()==tS)
      {
       if(txT.getText().equals("?"))
  {txT.setText("");
   txT.setBackground(Color.white);
      }    
tUnit="s";
txT.setEditable(true);
txT.setBackground(Color.white);
      }
else if(ie.getSource()==tH)
{
  if(txT.getText().equals("?"))
  {txT.setText("");
   txT.setBackground(Color.white);
      } 
  tUnit="h";
txT.setEditable(true);
txT.setBackground(Color.white);
}
else if(ie.getSource()==tD)
{
 if(txT.getText().equals("?"))
  {txT.setText("");
   txT.setBackground(Color.white);
      }  
tUnit="d";
txT.setEditable(true);
txT.setBackground(Color.white);
}
else if(ie.getSource()==tReq)
{
 tUnit="?";
  txT.setEditable(false);
  txT.setText(tUnit);
  txT.setBackground(c3);
}
   

      if(ie.getSource()==sM)
      {
        if(txS.getText().equals("?"))
  {txS.setText("");
   txS.setBackground(Color.white);
      } 
        sUnit="m";
        txS.setEditable(true);
        txS.setBackground(Color.white);
      }
else if(ie.getSource()==sKm)
{
      
        if(txS.getText().equals("?"))
  {txS.setText("");
   txS.setBackground(Color.white);
      } 
sUnit="km";
txS.setEditable(true);
txS.setBackground(Color.white);
}
else if(ie.getSource()==sMil)
{
        if(txS.getText().equals("?"))
  {txS.setText("");
   txS.setBackground(Color.white);
      } 
sUnit="miles";
txS.setEditable(true);
txS.setBackground(Color.white);
}
else if(ie.getSource()==sReq)
{
  sUnit="?";
  txS.setEditable(false);
  txS.setText(sUnit);
  txS.setBackground(c3);
}
   
      



}

}//end ofrBItemListener
  private class butActionListener implements ActionListener{

public void actionPerformed(ActionEvent ae)
{
  if(ae.getSource()==calculate) 
  {
if(viUnit=="?" || vfUnit=="?" || aUnit=="?" || tUnit=="?" || sUnit=="?")     //1st if
{
if((viUnit=="?" && vfUnit=="?" && aUnit=="?") ||     //2nd if
   (vfUnit=="?" && viUnit=="?" && sUnit=="?") ||
   (vfUnit=="?" && viUnit=="?" && tUnit=="?") ||
   (vfUnit=="?" && aUnit=="?" && sUnit=="?") ||
   (vfUnit=="?" && aUnit=="?"  && tUnit=="?") ||
   (vfUnit=="?" && sUnit=="?"  && tUnit=="?") ||
   (viUnit=="?" && sUnit=="?"  && aUnit=="?") ||
   (viUnit=="?" && sUnit=="?"  && tUnit=="?") ||
   (viUnit=="?" && aUnit=="?"  && tUnit=="?") ||
   (tUnit=="?"  && aUnit=="?"  && sUnit=="?")    )
{

  if(vfUnit=="?")
txVf.setBackground(Color.red);
  if(viUnit=="?")
txVi.setBackground(Color.red);
  if(sUnit=="?")
txS.setBackground(Color.red);
  if(aUnit=="?")
txA.setBackground(Color.red);
  if(tUnit=="?")
txT.setBackground(Color.red);
  java.awt.Toolkit.getDefaultToolkit().beep();
   JOptionPane.showMessageDialog(frame,"Select maximum two parameters as Required?","Message",JOptionPane.WARNING_MESSAGE);
}  
else                            //2nd  else                      
{
if((!txVf.getText().trim().equals("") && !txVi.getText().trim().equals("") && !txA.getText().trim().equals("")) ||    //3rd if
     (!txVf.getText().trim().equals("") && !txVi.getText().trim().equals("") && !txS.getText().trim().equals("")) ||
     (!txVf.getText().trim().equals("") && !txVi.getText().trim().equals("") && !txT.getText().trim().equals("")) ||
     (!txVf.getText().trim().equals("") && !txA.getText().trim().equals("")  && !txS.getText().trim().equals("")) ||
     (!txVf.getText().trim().equals("") && !txA.getText().trim().equals("")  && !txT.getText().trim().equals("")) ||
     (!txVf.getText().trim().equals("") && !txS.getText().trim().equals("")  && !txT.getText().trim().equals("")) ||
     (!txVi.getText().trim().equals("") && !txS.getText().trim().equals("")  && !txA.getText().trim().equals("")) ||
     (!txVi.getText().trim().equals("") && !txS.getText().trim().equals("")  && !txT.getText().trim().equals("")) ||
     (!txVi.getText().trim().equals("") && !txA.getText().trim().equals("")  && !txT.getText().trim().equals("")) ||
     (!txT.getText().trim().equals("")  && !txA.getText().trim().equals("")  && !txS.getText().trim().equals(""))    )
{ if((!vfUnit.equals("nounit")&& !viUnit.equals("nounit")&& !aUnit.equals("nounit")) ||    //unit checking if
     (!vfUnit.equals("nounit")&& !viUnit.equals("nounit")&& !sUnit.equals("nounit")) ||
     (!vfUnit.equals("nounit")&& !viUnit.equals("nounit")&& !tUnit.equals("nounit")) ||
     (!vfUnit.equals("nounit")&& !aUnit.equals("nounit") && !sUnit.equals("nounit")) ||
     (!vfUnit.equals("nounit")&& !aUnit.equals("nounit") && !tUnit.equals("nounit")) ||
     (!vfUnit.equals("nounit")&& !sUnit.equals("nounit") && !tUnit.equals("nounit")) ||
     (!viUnit.equals("nounit")&& !sUnit.equals("nounit") && !aUnit.equals("nounit")) ||
     (!viUnit.equals("nounit")&& !sUnit.equals("nounit") && !tUnit.equals("nounit")) ||
     (!viUnit.equals("nounit")&& !aUnit.equals("nounit") && !tUnit.equals("nounit")) ||
     (!tUnit.equals("nounit") && !aUnit.equals("nounit") && !sUnit.equals("nounit"))    )
{                            //unit checking if
  try
  {
   NumberFormat nf=NumberFormat.getNumberInstance();
nf.setMaximumFractionDigits(7);
   if(vfUnit=="?" && viUnit=="?")
{
unitConverFunc();
vf=((s/t)+((a*t)/2));
vi=((s/t)-((a*t)/2));
tAns.setText("Final Velocity (vf)="+nf.format(vf)+" m/s\nInitial Velocity (vi)="+nf.format(vi)+" m/s");
tPro.setText("  Final Velocity:\n\n  We know that\n      vf=vi+at _______________(1)\n  and\n      s=vit+0.5att\n=> vi=s/t-0.5at ____________(2)"
               +"\n  by putting ___(2) in ___(1)\n  We get \n       vf=s/t+0.5at ___________(final)\n\n  Initial Velocity:\n\n We know that"
               +"\ns=vit+0.5att\n=>vi=s/t-0.5at___________(final)");

}
 else if(vfUnit=="?" && viUnit=="nounit")
{
unitConverFunc();
vf=((s/t)+((a*t)/2));
tAns.setText("Final Velocity (vf)="+nf.format(vf)+" m/s");
tPro.setText("  Final Velocity:\n\n  We know that\n      vf=vi+at _______________(1)\n  and\n      s=vit+0.5att\n=> vi=s/t-0.5at ____________(2)"
               +"\n  by putting ___(2) in ___(1)\n  We get \n       vf=s/t+0.5at ____________(final)");


}
 else if(vfUnit=="nounit" && viUnit=="?")
{
unitConverFunc();
vi=((s/t)-((a*t)/2));

tAns.setText("  Initial Velocity (vi)="+nf.format(vi)+" m/s");
tPro.setText("  Initial Velocity:\n\n  We know that\ns=vit+0.5att\n=>vi=s/t-0.5at___________(final)");
}




else if(vfUnit=="?" && sUnit=="?")
{
unitConverFunc();
vf=(vi+(a*t));
s=((vi*t)+((a*t*t)/2));
tAns.setText("Final Velocity (vf)="+nf.format(vf)+" m/s\nDistance (s)="+nf.format(s)+" m");
tPro.setText("  Final Velocity:\n\n  We know that\n       vf=vi+at_____________(final)\n\n  Distance:\n\n  We know that\n       s=vit+0.5att________(final)");


}
 else if(vfUnit=="?" && sUnit=="nounit")
{
unitConverFunc();
vf=(vi+(a*t));
tAns.setText("Final Velocity (vf)="+nf.format(vf)+" m/s");
tPro.setText("  Final Velocity:\n\nWe know that\n       vf=vi+at_____________(final)");

}
 else if(vfUnit=="nounit" && sUnit=="?")
{
unitConverFunc();
s=((vi*t)+((a*t*t)/2));

tAns.setText("Distance (s)="+nf.format(s)+" m");
tPro.setText("  Distance:\n\n  We know that\n       s=vit+0.5att________(final)");
}


 else if(vfUnit=="?" && aUnit=="?")
{
unitConverFunc();
vf=(((2*s)/t)-vi);
a=(((2*s)-(2*vi*t))/t*t);
tAns.setText("Final Velocity (vf)="+nf.format(vf)+" m/s\nAccelaration (a)="+nf.format(a)+" m/ss");


tPro.setText("  Final Velocity:\n\n  We know that\n       vf=vi+at_____________(1)\nand\n    s=vit+0.5att\n  => a=(2s-2vit)/tt_________(2)"             
               +"\n  by putting ____(2) in ____(1)   We get \n vf=((2s)/t)-vi________(final)\n\n  Accelaration:\n\n  We know"
               +" that \n      s=vit+0.5att\n=> a=(2s-2vit)/tt_________(final)");
}
 else if(vfUnit=="nounit" && aUnit=="?")
{
unitConverFunc();
a=(((2*s)-(2*vi*t))/t*t);
tAns.setText("Accelaration (a)="+nf.format(a)+" m/ss");
tPro.setText("  Accelaration:\n\n  We know"
               +" that \n      s=vit+0.5att\n=> a=(2s-2vit)/tt_________(final)");
}
 else if(vfUnit=="?" && aUnit=="nounit")
{
unitConverFunc();
vf=(((2*s)/t)-vi);
tAns.setText("Final Velocity (vf)="+nf.format(vf)+" m/s");
tPro.setText("  Final Velocity:\n\n  We know that\n       vf=vi+at_____________(1)\n and\n    s=vit+0.5att\n  => a=(2s-2vit)/tt_________(2)"             
               +"\n  by putting ____(2) in ____(1)   We get \n vf=((2s)/t)-vi________(final)");
}

 else if(vfUnit=="?" && tUnit=="?")
{
unitConverFunc();
vf=Math.sqrt((vi*vi)+(2*a*s));
t=(((Math.sqrt((vi*vi)+(2*a*s)))-vi)/a);
tAns.setText("Final Velocity (vf)="+nf.format(vf)+" m/s\nTime (t)="+nf.format(t)+" s");
tPro.setText("  Final Velocity:\n\n  We know that\n      2as=vfvf-vivi\n => vf=SquareRoot(vivi+2as)________(final)\n\n  Time:\n\n"
               +"  We know that\n      vf=vi+at\n => t=(vf-vi)/a__________________(1)\n and\n    2as=vfvf-vivi\n => vf=SquareRoot(vivi+2as)"
               +"_____(2)\n  by putting ____(2) in ____(1)\n  We get\n    t=(SquareRoot(vivi+2as)-vi)/a_____(final)");


}
else  if(vfUnit=="?" && tUnit=="nounit")
{
unitConverFunc();
vf=Math.sqrt((vi*vi)+(2*a*s));

tAns.setText("Final Velocity (vf)="+nf.format(vf)+" m/s");
tPro.setText("  Final Velocity:\n\n  We know that\n      2as=vfvf-vivi\n => vf=SquareRoot(vivi+2as)________(final)");

}

else if(vfUnit=="nounit" && tUnit=="?")
{
unitConverFunc();

t=(((Math.sqrt((vi*vi)+(2*a*s)))-vi)/a);

tAns.setText("Time (t)="+nf.format(t)+" s");
tPro.setText("  Time:\n\n"
               +"  We know that\n      vf=vi+at\n => t=(vf-vi)/a__________________(1)\n and\n    2as=vfvf-vivi\n => vf=SquareRoot(vivi+2as)"
               +"_____(2)\n  by putting ____(2) in ____(1)\n  We get\n    t=(SquareRoot(vivi+2as)-vi)/a_____(final)");
}

else if(viUnit=="?" && sUnit=="?")
{
unitConverFunc();
vi=(vf-(a*t));
s=((vf*t)-(0.5*a*t*t));
tAns.setText("Initial Velocity (vi)="+nf.format(vi)+" m/s\nDistance (s)="+nf.format(s)+" m");
tPro.setText("  Initial Velocity:\n\n  We know that\n      vf=vi+at\n => vi=vf-at_______(final)\n\n  Distance:\n\n"
               +"  We know that\n       vf=vi+at\n => vi=vf-at________(1)\n\n and\n\n    s=vit+0.5att__________(2)"
               +"\n by putting  ____(1)  in  ____(2)\n  We get\n    s=vft-0.5att________(final)");

}
else if(viUnit=="?" && sUnit=="nounit")
{
unitConverFunc();
vi=(vf-(a*t));
tAns.setText("Initial Velocity (vi)="+nf.format(vi)+" m/s");
tPro.setText("  Initial Velocity:\n\n  We know that\n      vf=vi+at\n => vi=vf-at_______(final)");
}
else if(viUnit=="nounit" && sUnit=="?")
{
unitConverFunc();
s=((vf*t)-(0.5*a*t*t));
tAns.setText("Distance (s)="+nf.format(s)+" m");
tPro.setText("  Distance:\n\n"
               +"  We know that\n       vf=vi+at\n => vi=vf-at________(1)\n\n and\n\n    s=vit+0.5att__________(2)"
               +"\n by putting  ____(1)  in  ____(2)\n  We get\n    s=vft-0.5att________(final)");

}

else if(viUnit=="?" && aUnit=="?")
{
unitConverFunc();
vi=(((2*s)/t)-vf);
a=(((2*vf)/t)-((2*s)/(t*t)));
tAns.setText("Initial Velocity (vi)="+nf.format(vi)+" m/s\nAccelaration (a)="+nf.format(a)+" m/ss");
tPro.setText("  Initial Velocity:\n\n  We know that\n       vf=vi+at\n => a=(vf-vi)/t____________(1)\n and\n      s=vit+0.5att"
               +"\n => vi=(s/t)-0.5at_________(2)\n  by putting  _____(1) in  _____(2)\n  We get\n    vi=(2s/t)-vf__________(final)"
               +"  \n\nAccelaration:\n\n  We know that\n       vf=vi+at\n => a=(vf-vi)/t________(1)\n and\n       s=vit+0.5att\n => vi=(s/t)-0.5at"
               +"___________(2)\n by putting  _____(2)  in  _____(1)\n  We get\n    a=(2vf/t)-(2s/tt)_________(final)");
}
else if(viUnit=="?" && aUnit=="nounit")
{
unitConverFunc();
vi=(((2*s)/t)-vf);
tAns.setText("Initial Velocity (vi)="+nf.format(vi)+" m/s");
tPro.setText("  Initial Velocity:\n\n  We know that\n       vf=vi+at\n => a=(vf-vi)/t____________(1)\n and\n      s=vit+0.5att"
               +"\n => vi=(s/t)-0.5at_________(2)\n  by putting  _____(1) in  _____(2)\n  We get\n    vi=(2s/t)-vf__________(final)");
}
 else if(viUnit=="nounit" && aUnit=="?")
{
unitConverFunc();
a=(((2*vf)/t)-((2*s)/(t*t)));
tAns.setText("Accelaration (a)="+nf.format(a)+" m/s");
tPro.setText(" Accelaration:\n\n  We know that\n       vf=vi+at\n => a=(vf-vi)/t________(1)\n and\n       s=vit+0.5att\n => vi=(s/t)-0.5at"
               +"___________(2)\n by putting  _____(2)  in  _____(1)\n  We get\n    a=(2vf/t)-(2s/tt)_________(final)");
 }

else if(viUnit=="?" && tUnit=="?")  
{
unitConverFunc();
vi=Math.sqrt((vf*vf)-(2*a*s));
t=((vf-(Math.sqrt((vf*vf)-(2*a*s))))/a);
tAns.setText("Initial Velocity (vi)="+nf.format(vi)+" m/s\nTime (t)="+nf.format(t)+" s");
tPro.setText("  Initial Velocity:\n\n  We know that\n      2as=vfvf-vivi\n => vi=SquareRoot(vfvf-2as)________(final)\n\n  "
               +"Time:\n\n  We know that\n      vf=vi+at\n => t=(vf-vi)/a___________________(1)\n and\n      2as=vfvf-vivi\n => vi=SquareRoot(vfvf-2as)"
               +"_________(2)\n by putting  ____(2)  in  ____(1)\n  We get\n    t=(vf-SquareRoot(vfvf_2as))/a_________(final)");
}
else if(viUnit=="?" && tUnit=="nounit")
{
unitConverFunc();
vi=Math.sqrt((vf*vf)-(2*a*s));
tAns.setText("Initial Velocity (vi)="+nf.format(vi)+" m/s");
tPro.setText("  Initial Velocity:\n\n  We know that\n      2as=vfvf-vivi\n => vi=SquareRoot(vfvf-2as)________(final)");
}
else if(viUnit=="nounit" && tUnit=="?")
{
unitConverFunc();
t=((vf-(Math.sqrt((vf*vf)-(2*a*s))))/a);
tAns.setText("Time (t)="+nf.format(t)+" s");
tPro.setText("  Time:\n\n  We know that\n      vf=vi+at\n => t=(vf-vi)/a___________________(1)\n and\n      2as=vfvf-vivi\n => vi=SquareRoot(vfvf-2as)"
               +"_________(2)\n by putting  ____(2)  in  ____(1)\n  We get\n    t=(vf-SquareRoot(vfvf_2as))/a_________(final)");
}

else if(sUnit=="?" && aUnit=="?")
{
unitConverFunc();
s=(((vf*t)+(vi*t))/2);
a=((vf-vi)/t);
tAns.setText("Distance (s)="+nf.format(s)+" m\nAccelaration (a)="+nf.format(a)+" m/ss");
tPro.setText("  Distance:\n\n  We know that\n      s=vit+0.5att_________(1)\n and\n      vf=vi+at\n => a=(vf-vi)/t___________(2)\n by putting"
               +"  ____(2)  in  ____(1)\n We get\n     s=(vft/2)+(vit/2)_____________(final)\n\n  Accelaration:\n\n We know that\n       vf=vi+at"
               +"\n => a=(vf-vi)/t_____________(final)");
}
else if(sUnit=="?" && aUnit=="nounit")
{
unitConverFunc();
s=(((vf*t)+(vi*t))/2);
tAns.setText("Distance (s)="+nf.format(s)+" m");
tPro.setText("  Distance:\n\n  We know that\n      s=vit+0.5att_________(1)\n and\n      vf=vi+at\n => a=(vf-vi)/t___________(2)\n by putting"
               +"  ____(2)  in  ____(1)\n We get\n     s=(vft/2)+(vit/2)_____________(final)");
}
else if(sUnit=="nounit" && aUnit=="?")
{
unitConverFunc();
a=((vf-vi)/t);
tAns.setText("Accelaration (a)="+nf.format(a)+" m/ss");
tPro.setText("  Accelaration:\n\n We know that\n       vf=vi+at"
               +"\n => a=(vf-vi)/t_____________(final)");
}

else if(sUnit=="?" && tUnit=="?")
{
unitConverFunc();
s=(((vf*vf)-(vi*vi))/(2*a));
t=((vf-vi)/a);
tAns.setText("Distance (s)="+nf.format(s)+" m\nTime (t)="+nf.format(t)+" s");
tPro.setText("  Distance:\n\n We know that\n       2as=vfvf-vivi\n => s=(vfvf-vivi)/2a__________(final)\n\n  Time:\n\n  We know that"
               +"\n      vf=vi+at\n => t=(vf-vi)/a___________(final)");
}
else if(sUnit=="?" && tUnit=="nounit")
{
unitConverFunc();
s=(((vf*vf)-(vi*vi))/(2*a));
tAns.setText("Distance (s)="+nf.format(s)+" m");
tPro.setText("  Distance:\n\n We know that\n       2as=vfvf-vivi\n => s=(vfvf-vivi)/2a__________(final)");
}
 else if(sUnit=="nounit" && tUnit=="?")
{
unitConverFunc();
t=((vf-vi)/a);
tAns.setText("Time (t)="+nf.format(t)+" s");
tPro.setText("  Time:\n\n  We know that"
               +"\n      vf=vi+at\n => t=(vf-vi)/a___________(final)");
}

else if(aUnit=="?" && tUnit=="?")
{
unitConverFunc();
a=(((vf*vf)-(vi*vi))/(2*s));
t=((2*s)/(vi+vf));
tAns.setText("Accelaration (a)="+nf.format(a)+" m/ss\nTime (t)="+nf.format(t)+" s");
tPro.setText("  Accelaration:\n\n  We know that\n       2as=vfvf-vivi\n => a=(vfvf-vivi)/2s____________(final)\n\n  Time:\n\n We know that\n      vf=vi+at\n => t=(vf-vi)/a"
               +"__________(1)\n and\n       2as=vfvf-vivi\n => a=(vfvf-vivi)/2s_________(2)\n by putting  _____(2)  in  _____(1)\n We get\n     t=2s/vf+vi___________(final)");
}
else if(aUnit=="?" && tUnit=="nounit")
{
unitConverFunc();
a=(((vf*vf)-(vi*vi))/(2*s));
tAns.setText("Accelaration (a)="+nf.format(a)+" m/ss");
tPro.setText("  Accelaration:\n\n  We know that\n       2as=vfvf-vivi\n => a=(vfvf-vivi)/2s____________(final)");

}
else if(aUnit=="nounit" && tUnit=="?")
{

unitConverFunc();
t=((2*s)/(vi+vf));
tAns.setText("Time (t)="+nf.format(t)+" s");
tPro.setText("  Time:\n\n We know that\n      vf=vi+at\n => t=(vf-vi)/a"
               +"__________(1)\n and\n       2as=vfvf-vivi\n => a=(vfvf-vivi)/2s_________(2)\n by putting  _____(2)  in  _____(1)\n We get\n      t=2s/vf+vi___________(final)");
}
else if(tUnit=="?" && vfUnit!="nounit" && viUnit!="nounit" && aUnit!="nounit" && sUnit!="nounit" ){                           // when four parameters are entered
unitConverFunc();
t=((vf-vi)/a);
tAns.setText("Time (t)="+nf.format(t)+" s");
tPro.setText("  Time:\n\n  We know that"
               +"\n      vf=vi+at\n => t=(vf-vi)/a___________(final)");

}
else if(sUnit=="?" && vfUnit!="nounit" && viUnit!="nounit" && aUnit!="nounit" && tUnit!="nounit"){

unitConverFunc();
s=(((vf*vf)-(vi*vi))/(2*a));
tAns.setText("Distance (s)="+nf.format(s)+" m");
tPro.setText("  Distance:\n\n We know that\n       2as=vfvf-vivi\n => s=(vfvf-vivi)/2a__________(final)");


}
else if(viUnit=="?" && vfUnit!="nounit" && sUnit!="nounit" && aUnit!="nounit" && tUnit!="nounit"){

unitConverFunc();
vi=(vf-(a*t));
tAns.setText("Initial Velocity (vi)="+nf.format(vi)+" m/s");
tPro.setText("  Initial Velocity:\n\n  We know that\n      vf=vi+at\n => vi=vf-at_______(final)");



}
else if(vfUnit=="?" && viUnit!="nounit" && sUnit!="nounit" && aUnit!="nounit" && tUnit!="nounit"){

unitConverFunc();
vf=(vi+(a*t));
tAns.setText("Final Velocity (vf)="+nf.format(vf)+" m/s");
tPro.setText("  Final Velocity:\n\nWe know that\n       vf=vi+at_____________(final)");
}
else if(aUnit=="?" && viUnit!="nounit" && sUnit!="nounit" && vfUnit!="nounit" && tUnit!="nounit"){


unitConverFunc();
a=((vf-vi)/t);
tAns.setText("Accelaration (a)="+nf.format(a)+" m/ss");
tPro.setText("  Accelaration:\n\n We know that\n       vf=vi+at"
               +"\n => a=(vf-vi)/t_____________(final)");


}
}                    //    try block ended
catch(Exception e){

java.awt.Toolkit.getDefaultToolkit().beep();
JOptionPane.showMessageDialog(frame,e,"Error",JOptionPane.WARNING_MESSAGE);

}
}              // unit checking if ended

else{
if(viUnit.equals("nounit"))
txVi.setBackground(Color.red);  
if(vfUnit.equals("nounit"))
txVf.setBackground(Color.red); 
if(aUnit.equals("nounit"))
txA.setBackground(Color.red); 
if(sUnit.equals("nounit"))
txS.setBackground(Color.red); 
if(tUnit.equals("nounit"))
txT.setBackground(Color.red); 
java.awt.Toolkit.getDefaultToolkit().beep();
JOptionPane.showMessageDialog(frame,"Select Units for the parameters...","Message",JOptionPane.WARNING_MESSAGE);

}

 }                           //3rd if   
else                                //3rd else
{
Color c=new Color(255,119,119);
if(txVf.getText().equals(""))
txVf.setBackground(c);
if(txVi.getText().equals(""))
txVi.setBackground(c);
if(txA.getText().equals(""))
txA.setBackground(c);
if(txS.getText().equals(""))
txS.setBackground(c);
if(txT.getText().equals(""))
txT.setBackground(c);
java.awt.Toolkit.getDefaultToolkit().beep();
JOptionPane.showMessageDialog(frame,"Enter the values for any three parameteres...","Message",JOptionPane.WARNING_MESSAGE);


}                   //end of 3rd if

}                        //end of 2nd if

  



}                        //1st if
else                     //1st else
{

txVi.setBackground(Color.red);
txVf.setBackground(Color.red);
txA.setBackground(Color.red);
txS.setBackground(Color.red);
txT.setBackground(Color.red);
java.awt.Toolkit.getDefaultToolkit().beep();
JOptionPane.showMessageDialog(frame,"Select minimum one or maximum two parameters as Required?...","Message",JOptionPane.WARNING_MESSAGE);


}                      //end of 1st if else stat
  }              //end calculate
  else if(ae.getSource()==reset)
  {
  
    if(viUnit!="?")
    {
  txVi.setText("");
    }
    if(sUnit!="?"){
  txS.setText("");
    }
    if( tUnit!="?")
    {
  txT.setText("");
    }
    if(aUnit!="?")
    {
  txA.setText("");
    }
    if(vfUnit!="?")
    {
  txVf.setText("");
    }
  
  }                          //end of  reset button
  else
  {
  
    System.exit(0);
  
  }
}                      //end of actionperformed func
}                           //end of butActionListener class
  private void unitConverFunc()
{
    
    if(viUnit=="ms")       //    initial velocity
{
      try{
vi=Double.parseDouble(txVi.getText());
      }
      catch(NumberFormatException e){
        txVi.setBackground(Color.red);
        java.awt.Toolkit.getDefaultToolkit().beep();
      JOptionPane.showMessageDialog(frame,"you have entered multiple points... \nOR you have not entered  any vlaue...","Warning",JOptionPane.WARNING_MESSAGE); 
     txVi.setBackground(Color.white);
      }
}
else if(viUnit=="kms")
{
  try{
vi=Double.parseDouble(txVi.getText());
vi=vi*1000;
  }
  catch(NumberFormatException e){
        txVi.setBackground(Color.red);
        java.awt.Toolkit.getDefaultToolkit().beep();
      JOptionPane.showMessageDialog(frame,"you have entered multiple points... \nOR you have not entered  any vlaue...","Warning",JOptionPane.WARNING_MESSAGE); 
     txVi.setBackground(Color.white);
      }
}
else if(viUnit=="kmh")
{
  try{
vi=Double.parseDouble(txVi.getText());
vi=((vi*1000)/3600);
  }
  catch(NumberFormatException e){
        txVi.setBackground(Color.red);
        java.awt.Toolkit.getDefaultToolkit().beep();
      JOptionPane.showMessageDialog(frame,"you have entered multiple points... \nOR you have not entered  any vlaue...","Warning",JOptionPane.WARNING_MESSAGE); 
     txVi.setBackground(Color.white);
      }
}

    
if(vfUnit=="ms")           //   final velocity
{
  try{
vf=Double.parseDouble(txVf.getText());
  }
  catch(NumberFormatException e){
        txVf.setBackground(Color.red);
        java.awt.Toolkit.getDefaultToolkit().beep();
      JOptionPane.showMessageDialog(frame,"you have entered multiple points... \nOR you have not entered  any vlaue...","Warning",JOptionPane.WARNING_MESSAGE); 
     txVf.setBackground(Color.white);
      }
}
else if(vfUnit=="kms")
{
  try{
vf=Double.parseDouble(txVf.getText());
vf=vf*1000;
  }
  catch(NumberFormatException e){
        txVf.setBackground(Color.red);
        java.awt.Toolkit.getDefaultToolkit().beep();
      JOptionPane.showMessageDialog(frame,"you have entered multiple points... \nOR you have not entered  any vlaue...","Warning",JOptionPane.WARNING_MESSAGE); 
     txVf.setBackground(Color.white);
      }
}
else if(vfUnit=="kmh")
{
  try{
    vf=Double.parseDouble(txVf.getText());
vf=((vf*1000)/3600);
  }
  catch(NumberFormatException e){
        txVf.setBackground(Color.red);
        java.awt.Toolkit.getDefaultToolkit().beep();
      JOptionPane.showMessageDialog(frame,"you have entered multiple points... \nOR you have not entered  any vlaue...","Warning",JOptionPane.WARNING_MESSAGE); 
     txVf.setBackground(Color.white);
      }
}
     
 if(sUnit=="m")            //   distance
{
   try{
s=Double.parseDouble(txS.getText());
   }
   catch(NumberFormatException e){
        txS.setBackground(Color.red);
        java.awt.Toolkit.getDefaultToolkit().beep();
      JOptionPane.showMessageDialog(frame,"you have entered multiple points... \nOR you have not entered  any vlaue...","Warning",JOptionPane.WARNING_MESSAGE); 
     txS.setBackground(Color.white);
      }
}
else if(sUnit=="km")
{
  try{
s=Double.parseDouble(txS.getText());
s=s*1000;
  }
  catch(NumberFormatException e){
        txS.setBackground(Color.red);
        java.awt.Toolkit.getDefaultToolkit().beep();
      JOptionPane.showMessageDialog(frame,"you have entered multiple points... \nOR you have not entered  any vlaue...","Warning",JOptionPane.WARNING_MESSAGE); 
     txS.setBackground(Color.white);
      }
}
else if(sUnit=="miles")
{
  try{
s=Double.parseDouble(txS.getText());
s=s*1.609*1000;
  }
  catch(NumberFormatException e){
        txS.setBackground(Color.red);
        java.awt.Toolkit.getDefaultToolkit().beep();
      JOptionPane.showMessageDialog(frame,"you have entered multiple points... \nOR you have not entered  any vlaue...","Warning",JOptionPane.WARNING_MESSAGE); 
     txS.setBackground(Color.white);
      }
}
if(tUnit=="s")      //          time
{
  try{
t=Double.parseDouble(txT.getText());
  }
  catch(NumberFormatException e){
        txT.setBackground(Color.red);
        java.awt.Toolkit.getDefaultToolkit().beep();
      JOptionPane.showMessageDialog(frame,"you have entered multiple points... \nOR you have not entered  any vlaue...","Warning",JOptionPane.WARNING_MESSAGE); 
     txT.setBackground(Color.white);
      }
}
else if(tUnit=="h")
{
  try{
t=Double.parseDouble(txT.getText());
t=t*3600;
  }
  catch(NumberFormatException e){
        txT.setBackground(Color.red);
        java.awt.Toolkit.getDefaultToolkit().beep();
      JOptionPane.showMessageDialog(frame,"you have entered multiple points... \nOR you have not entered  any vlaue...","Warning",JOptionPane.WARNING_MESSAGE); 
     txT.setBackground(Color.white);
      }
}
else if(tUnit=="d")
{
  try{
t=Double.parseDouble(txT.getText());
t=t*24*3600;
  }
  catch(NumberFormatException e){
        txT.setBackground(Color.red);
        java.awt.Toolkit.getDefaultToolkit().beep();
      JOptionPane.showMessageDialog(frame,"you have entered multiple points... \nOR you have not entered  any vlaue...","Warning",JOptionPane.WARNING_MESSAGE); 
     txT.setBackground(Color.white);
      }
}

if(aUnit=="mss")       //accelaration
{
  try{
a=Double.parseDouble(txA.getText());
  }
  catch(NumberFormatException e){
        txA.setBackground(Color.red);
        java.awt.Toolkit.getDefaultToolkit().beep();
      JOptionPane.showMessageDialog(frame,"you have entered multiple points... \nOR you have not entered  any vlaue...","Warning",JOptionPane.WARNING_MESSAGE); 
     txA.setBackground(Color.white);
      }
}
else if(aUnit=="kmss")
{
  try{
a=Double.parseDouble(txA.getText());
a=a*1000;
  }
   catch(NumberFormatException e){
        txA.setBackground(Color.red);
        java.awt.Toolkit.getDefaultToolkit().beep();
      JOptionPane.showMessageDialog(frame,"you have entered multiple points... \nOR you have not entered  any vlaue...","Warning",JOptionPane.WARNING_MESSAGE); 
     txA.setBackground(Color.white);
      }
}
else if(aUnit=="kmhh")
{
  try{
a=Double.parseDouble(txA.getText());
a=((a*1000)/12960000);
  }
   catch(NumberFormatException e){
        txA.setBackground(Color.red);
        java.awt.Toolkit.getDefaultToolkit().beep();
      JOptionPane.showMessageDialog(frame,"you have entered multiple points... \nOR you have not entered  any vlaue...","Warning",JOptionPane.WARNING_MESSAGE); 
     txA.setBackground(Color.white);
      }
}

    
    
   
    
    
  
  
  }
  private class KeyChecking extends KeyAdapter{
  
  public void keyTyped(KeyEvent e)
       {
        char ch = e.getKeyChar(); // Get the typed character  
         // Don't ignore backspace or delete  
       if (ch != KeyEvent.VK_BACK_SPACE && ch != KeyEvent.VK_DELETE && ch!=KeyEvent.VK_PERIOD && ch!=KeyEvent.VK_ENTER && ch!=KeyEvent.VK_MINUS) 
         {  
            if (!(ch == '0' || ch == '1' || ch == '2' || ch == '3' || ch == '4' || ch == '5' || ch == '6' || ch == '7' || ch == '8' || ch == '9')) 
           {
            e.consume();  // Ignore this key  
            java.awt.Toolkit.getDefaultToolkit().beep();
          JOptionPane.showMessageDialog(frame,"Only Digits are Allowed...","Warning",JOptionPane.WARNING_MESSAGE);
            }
         }
     
     
  if(ch==KeyEvent.VK_ENTER){
      calculate.doClick();
       }
  }
   
      

  
  } 
  
 
  

Uam(){
  initGUI();
  }
  
}


class StartSplashScreen extends JWindow {
  private int duration;
  public StartSplashScreen(int d) {
    duration = d;
  }

  // A simple little method to show a title screen in the center
  // of the screen for the amount of time given in the constructor
  public void showSplash() {
    JPanel content = (JPanel)getContentPane();
    content.setBackground(Color.white);
JPanel panel=new JPanel();


    // Set the window's bounds, centering the window
    int width = 450;
    int height =120;
    Dimension screen = Toolkit.getDefaultToolkit().getScreenSize();
    int x = (screen.width-width)/2;
    int y = (screen.height-height)/2;
    setBounds(x,y,width,height);

    // Build the splash screen
   
    JLabel label1 = new JLabel("I have tried my best to make the software perfect.But if there is any error");
    JLabel label2 = new JLabel("or bug then kindly inform me and obliged me. The software is under ");
     JLabel label3 = new JLabel("processing,there are some features which will be available in the ");
     JLabel label4 = new JLabel("coming version.");

    
    panel.add(label1);
    panel.add(label2);
    panel.add(label3);
    panel.add(label4);
    JLabel copyrt = new JLabel
      ("https://www.facebook.com/irfan.gomalian", JLabel.CENTER);
    copyrt.setFont(new Font("Sans-Serif", Font.BOLD, 12));
    content.add(panel, BorderLayout.CENTER);
    content.add(copyrt, BorderLayout.SOUTH);
    Color oraRed = new Color(156, 20, 20,  255);
    content.setBorder(BorderFactory.createLineBorder(oraRed, 10));

    // Display it
    setVisible(true);

    // Wait a little while, maybe while loading resources
    try { Thread.sleep(duration); } catch (Exception e) {}

    setVisible(false);
  }

  public void showSplashAndExit() {
    showSplash();
    
  }


}
 