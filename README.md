package coolwinks;

import java.util.List;

import org.openqa.selenium.By;
import org.openqa.selenium.JavascriptExecutor;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.testng.annotations.Test;

public class Testpage {
	@Test
	public void coolwinks() throws Throwable {
		System.setProperty("webdriver.chrome.driver", "F:\\D\\Drivers\\Chrome\\chromedriver_win32\\chromedriver.exe");

		WebDriver driver = new ChromeDriver();
		JavascriptExecutor js = (JavascriptExecutor) driver;

		driver.manage().window().maximize();

		driver.get("https://www.coolwinks.com/");
		Thread.sleep(1000);

		// The script needs to start from the home page, then category page and finally add to cart from the product page.
		driver.findElement(By.xpath("//*[@id=\"dialog\"]/span")).click();
		driver.findElement(By.xpath("//*[@id=\"abcd\"]/div[3]/div/ul/li[2]")).click();
		driver.findElement(By.id("userEmailNR")).sendKeys("rinklegarg98@gmail.com");
		driver.findElement(By.id("userPwdNR")).sendKeys("cw_ze531o");
		driver.findElement(By.xpath("//*[@id=\"abcd\"]/div[3]/div/ul/li[2]/div[2]/form/div[1]/input")).click();
		Thread.sleep(1000);
		driver.findElement(By.cssSelector("#collections")).click();

		driver.findElement(By.xpath("//*[@id=\"container\"]/div[4]/section/div[2]/ul/li[2]/div[2]")).click();
		driver.findElement(By.xpath("//*[@id=\"brandAlias\"]")).click();
		Thread.sleep(1000);
		driver.findElement(By.xpath("//*[@id=\"JRS\"]")).click();

		js.executeScript("window.scrollBy(244,210)");
		driver.findElement(By.xpath("//*[@id=\"container\"]/div[6]/div[2]/ul/li[1]/div[1]/a")).click();
		js.executeScript("window.scrollBy(478,468)");
		driver.findElement(By.xpath("//*[@id=\"container\"]/aside/div[2]/div[2]/div[11]/input[2]")).click();
		driver.findElement(By.xpath("//*[@id=\"P50B2692_246\"]")).click();
	}
}
