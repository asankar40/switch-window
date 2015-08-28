# switch-window
package swit;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;

public class wind {

	public static void main(String[] args)  {
		// TODO Auto-generated method stub
		
		WebDriver driver = new FirefoxDriver();
		driver.get("http://www.tnstc.in");
		driver.manage().window().maximize();
		String pw = driver.getWindowHandle();
		//Thread.sleep(30000);
		driver.findElement(By.xpath("html/body/table/tbody/tr/td[2]/table/tbody/tr[4]/td[1]/table/tbody/tr[3]/td/a/img")).click();
		for(String handle : driver.getWindowHandles())
		{
			driver.switchTo().window(handle);
		}
		driver.findElement(By.name("txtUserLoginID")).sendKeys("sankar");
		driver.findElement(By.name("txtPassword")).sendKeys("123sss");
		driver.switchTo().window(pw);
		
	}

}

