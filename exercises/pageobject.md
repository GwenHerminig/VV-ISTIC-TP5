## Page Object Model

The image below shows the poll page of the [Simba Organizer](https://github.com/barais/doodlestudent/) application discussed in classes.

![Simba Organizer Poll page](simba-poll-page.png)

Write in this document the interface of a page object class for this page.

## Answer
HAMONO Hermine et ROY Raphaël
```
class MyPageObject:
    def __init__(self, driver):
        self.driver = driver

    def enter_name(self, name):
        element = self.driver.find_element(*MainPageLocators.NAME)
        element.send_keys(name)
        

    def enter_email(self, email):
        element = self.driver.find_element(*MainPageLocators.EMAIL)
        element.send_keys(email)

    def switch_agenda_flux(self):
        element = self.driver.find_element(*MainPageLocators.AGENDA_SWITCH)
        element.click()
        

    def switch_alimentary_preferences(self):
        element = self.driver.find_element(*MainPageLocators.PREFERENCES_SWITCH)
        element.click()

    def switch_to_tab_view(self):
        element = self.driver.find_element(*MainPageLocators.TAB_BUTTON)
        element.click()
    
    def switch_to_calendar_view(self):
        element = self.driver.find_element(*MainPageLocators.CALENDAR_BUTTON)
        element.click()
        

    def check_date(self, date):
        element = self.driver.find_element(By.XPATH, "//input[@id='date']")
        element.click()

    def validate(self):
        element = self.driver.find_element(*MainPageLocators.VALIDATE)
        element.click()
        

    def enter_commentary_name(self, name):
        element = self.driver.find_element(*MainPageLocators.NAME_COMMENTARY)
        element.send_keys(name)
        

    def enter_commentary(self, commentary):
        element = self.driver.find_element(*MainPageLocators.COMMENTARY)
        element.send_keys(commentary)
        

    def send_commentary(self):
        element = self.driver.find_element(*MainPageLocators.COMMENTARY_SEND)
        element.click()
  
