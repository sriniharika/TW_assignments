import processing.core.PApplet;

public class fourBall extends PApplet {

//    list of all the constants and variables used! (Global Variables are bad practice!! Oops!)
    public static final int WIDTH = 600;
    public static final int HEIGHT = 600;
    public static final int RADIUS1 = 10;
    public static final int BGCOLOR = 255;
    public static final int distanceDivisor = 6;
    public static final int speed1 = 1;
    public static final int speed2 = 2;
    public static final int speed3 = 3;
    public static final int speed4 = 4;
    int x1 =0;
    int x2 =0;
    int x3 =0;
    int x4 =0;

    public static void main(String[] args) {
        PApplet.main("fourBall",args);
    }

    @Override
    public void settings() {
        super.settings();
//        sets the size of window to defined constants
        size(WIDTH, HEIGHT);
    }

    @Override
    public void draw() {
//        uncomment following line to remove trails left by balls
//        getBackground();
        
//        draws four circles
        getEllipse(1,x1);
        getEllipse(2,x2);
        getEllipse(3,x3);
        getEllipse(4,x4);

//        this method changes displacement-vectors to move the ball
        changeDistance();
    }

    private void getEllipse(int distance, int displacementVector) {
        ellipse(displacementVector,  (HEIGHT * distance) /distanceDivisor, RADIUS1, RADIUS1);

    }

    private void changeDistance(){
        x1+= speed1;
        x2+= speed2;
        x3+= speed3;
        x4+= speed4;
    }

    private void getBackground() {
        background(BGCOLOR);
    }
}