# Avinas-QA
Practice codes
package website;

import java.util.List;
import java.util.concurrent.TimeUnit;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.firefox.FirefoxDriver;
import org.openqa.selenium.interactions.Actions;
import org.openqa.selenium.support.ui.Select;


public class Testing {

	public static void main(String[] args) throws InterruptedException {
		// TODO Auto-generated method stub

	System.setProperty("webdriver.chrome.driver","C:\\Users\\AVINS\\Desktop\\New folder\\chromedriver.exe");	
		  //FirefoxDriver f1 = new FirefoxDriver();
		ChromeDriver f1 = new ChromeDriver();
		f1.manage().window().maximize();
		f1.get("http://www.golfclubs.com");
		 
		  Thread.sleep(2000);
		  f1.findElementByName("q").sendKeys("golf");
		  f1.findElementByXPath(".//*[@id='navbar-slide']/div[2]/div/form[1]/div/span/button").click();
	      f1.manage().timeouts().implicitlyWait(10, TimeUnit.SECONDS);
	      
	    
	        List allChkBoxList = f1.findElementsByName("filter_spec_1212_opt_ti");
	    
	        int boxsize = allChkBoxList.size();
	        System.out.println(allChkBoxList);
	        System.out.println(boxsize);
	        
	        for(int i=0; i<boxsize; i++ )
	        {
	        	f1.findElements(By.name("filter_spec_1212_opt_ti")).get(i).click();
	        }
	        
	        new Select (f1.findElementById("filter_by_brand-form")).selectByValue("1");
	        Thread.sleep(2000);
	        new Select (f1.findElementById("filter_by_category-form")).selectByValue("3858");
	        Thread.sleep(2000);
	       // new Select (f1.findElementById("filter_by_price-form")).selectByVisibleText("$75 to $200 (4)" );
	        
	        f1.findElementByLinkText("Accessories").click();
	        f1.findElement(By.linkText("Men's Sunglasses")).click();
	        Thread.sleep(2000);
	        f1.findElementByLinkText("Oakley Sliver").click();
	
	        
	        List<WebElement> radbtn = f1.findElementsByXPath("//input[@type='radio']");
	        int abc = radbtn.size();
	        System.out.println(abc); 	   
	        f1.findElementsByXPath("//input[@type='radio']").get(2).click();
	        Thread.sleep(2000);
	    	   
	    	   
	    	   
	    	   
	    	   
	    	   
	        
	      f1.quit();  
	}

}
