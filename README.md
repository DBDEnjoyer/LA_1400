# LA_1400
{
{
package Grigioni.Leonardo.fieseliese;
import robocode.*;
public class schlecht extends JuniorRobot
{
	public void TurnAndShoot(){
		int shotcounter = 1;
		int negativedistance = 1200 - scannedDistance;
		int degrees = negativedistance / 399;
		int recoilcontroll = negativedistance / 1000 ;
		fire(2.95);	
		if (shotcounter == 1)
		{
					turnGunLeft(degrees);
					shotcounter++ ;		
		}
		if (shotcounter == 2)
		{
					turnGunLeft(degrees-recoilcontroll);
					shotcounter++ ;		
		}
		if (shotcounter == 3)
		{
					turnGunLeft(degrees-recoilcontroll);
					shotcounter = 1;		
		}
	}	
	public void run() {	
		setColors(black, black, red, red, black);
		while(true) {
			turnRight(3);
			ahead(3);
		}
	}

	public void onScannedRobot() {
		TurnAndShoot();
	}
	
	public void onHitByBullet() {		
	}
	
	public void onHitWall() {
	}
}
