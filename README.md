# Test-Driven-Development with Python step by step code-along
https://www.obeythetestinggoat.com/

## Part 1: The fundamental workflow of TDD and a gentle introduction to Django 
Setup according to instructions went really smoothly, which was really nice. 
The instructions were also clear, so very easy to code along. _Quite soon I got 
into the habit to first try to think about what the next step should be after 
finishing a piece of code, or after updating a test and getting a new failure._ 
This practice helped keeping me more engaged.

I really appreciate how unit testing and functional testing are handled in 
parallel, as that keeps the focus both on the low level internal consistency, 
but also tying back to the user story level to ensure the code actually is 
achieving something of use.

## Part 2: Real Developers Ship

**8. Prettification: Layout and Styling, and What to Test About It**
Quick intro to bootstrap and django templating.

**9. Testing Deployment Using a Staging Site**
Pushing you to setup the site on an actual server and get a proper domain. 
Really appreciated the push, and it went smoothly to set it up in AWS, though 
I expect that for a beginner with no previous experience of servers, this might 
have been a very steep learning curve.

**10. Getting to a Production-Ready Deployment**
Installing and configuring nginx and gunicorn in order to replace the Django 
built-in server. Further, updating settings.py to look for environment variables 
so that debug and allowed_hosts have more secure settings in production mode.

Overall straight forward, but a good reminder of how much time you can end up 
spending on troubleshooting the smallest typo when it comes to server 
configurations.

**11. Automating Deployment with Fabric**
Excellent chapter that shows both how easy deployment becomes with Fabric, but 
also some really neat CL commands to work with template files. No matter how 
much else from this book I actually end up using, I'm sure this will come in 
handy on many occasions.

Example; ```cat ./deploy_tools/gunicorn-systemd.template.service \ 
| sed "s/DOMAIN/prod.randomtechramblings.com/g" \ 
| sudo tee /etc/systemd/system/gunicorn-prod.randomtechramblings.com.service```

**12. Splitting Our Tests into Multiple Files, and a Generic Wait Helper**
Quick chapter just to refactor the tests into a more maintainable structure.

**13. Validation at the Database Layer**
Starting to add a bit more Django magic to help out with routing and form 
validation.

**14. A Simple Form**
Long chapter introducing Django forms, and a bit intentionally tedious 
refactoring to really push for TDD discipline. As my interest lies more 
in learning more Python and TDD than Django, some of the content felt 
less interesting than many of the previous chapters.

One thing to remember; self.fail(object) prints the object to the CL, 
which can help a lot when debugging failing tests...

**15. More Advanced Forms**
Guess I want to be a completionist in regards to this book, because I went 
through this chapter too though it was clearly marked as optional. Hopefully, 
getting a bit more familiarity with the Django forms will come in handy at some 
point in the future.

**16. Dipping Our Toes, Very Tentatively, into JavaScript**
Short chapter with just the bare minimums, which suits me quite nice. I 
would though have appreciated a bit of discussion on the duplication of 
html code, when the unit test doesn't actually test the django template 
it seems like it's bound to happen that the markup there at some point 
will change, without the javascript test being properly updated.

**17. Deploying Our New Code**
Another short chapter, since the release process was semi automated already. 

## Part 3: More Advanced Topics in Testing

**18. User Authentication, Spiking, and De-Spiking**
Example of doing a quick and dirty proof of concept first to assure that 
a solution is viable, and once proven to scrap it and rewrite the code 
using TDD.

**19. Using Mocks to Test External Dependencies or Reduce Duplication**
Finishing up auth functionality along with tests that mocks the e-mail 
send out. Back to focus on the core python unit test packages, which I 
appreciate.

**20. Test Fixtures and a Decorator for Explicit Waits**
Adding fixtures to help test isolated parts more efficiently without 
having to go through the whole setup process (eg. logging in) every 
time in the browser.

Further, providing a neat example of creating a decorator in order to 
avoid duplicate code.