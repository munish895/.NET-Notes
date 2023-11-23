# .net interview preparation -> 


### const keyword - 
const keyword is used to declare the variable which can't be changed during its lifecycle. we need to initialize the variable's value at the time of declaration.
we can't change the value of the variable once its declared.

 public/private const string name = 'dhruv Sharma';

###  ReadOnly keyword - 
can be used to declare the variable whose value needs to initialize at the time of declaration. Its value can only be update in the constructor else u can't
update the variable's value during its lifecycle.

  public/private readonly string name = 'Dhruv SHarma';

### Static keyword - 
It allows u to declare the static member which belongs to the type itself instead of object. 

### Encapsulation/Inheritance/Polymorphism 

#### Encapsulation - 
 encapsulation is considered as the first principle of OOPs. through encapsulation one class/struct can define the accessibility of its member/functions outside 
 of the class. Can that function/member be accessible outside the class or not. This is done due to keep the standards and to avoid any extra coding errors. Encapsulation is more 
 of like the capsule keeps the all powder in itself. 
 
#### Inheritance - 
 Inheritance is one of the principle of the OOP. through inheritence we can use the function of 1 class into the other class. the class of which we are using the 
 function is known as base class and the class in which we are using that function is known as derived class. OR Parent and Child class. Inheritance is of 3 to 4 types:
 Single inheritence, multiple inheritence, multilevel inheritence. C# does not support multiple inheritence means one class can't be inherit from more than 1 class. but multiple
 inheritance can be achieved using interfaces. 
 
#### Polymorphism - 
 Polymorphism is one of the principle of the OOP. polymorphism means one word many forms. it is of 2 types. Method Overloading, Method overriding. 
 
### IN, REF and OUT keyword - 

IN variable - In variable must be initialized before passing to any called method. Its value can't be updated in the called method. If u try to update the value of the in 
variable in the called method it will throw an error. So it's like a readonly variable only.

REF - Ref is also like the in variable and it must be initialized before passing to any called method. but its value can be updated in the called method. ref keyword causes an 
argument to be passed by reference. 

OUT - for out keyword its not necessary to initialize it before passing to any called method. it goes naked in the called method and its value will be update in the called 
method. it will comes out with the clothes. 

- Method hiding or method shadowing - method hiding is the also known as method shadowing. shadowing is a vb.net concept. if u don't want to override the base class method 
in the child class then its method hiding and you are using the same method definition in the child class. Method hiding can be achieved by using new keyword. in method hiding 
you use the new keyword to hiding the base class implementation of the base class method.  

for eg. like
class A{

public void Display(){
Console.WriteLine('A')
}
}

class B : C{
public void Display(){
Console.WriteLine('B')}}

class D{

B objecct = new B()
b.voidDisplay()
}

OUTPUT -> Now the above command will print the 'B' on the console but with a warning that if u want the method hiding then use new keyword.

now if in the class B if u do use 

new public void Display{
COnsole.WriteLine('B'){
It will not throw the error. and the method hiding will get achieved.


boxing and unboxing

boxing - boxing is the process of converting a value type variable into an object type or to any interface type implemented by this value type. When a CLR does this boxing 
means wraps the value inside an System.Object instance and stores it inside the managed heap. Boxing is implicit but unboxing not.  Whereas unboxing is to convert the object into 
a value type. OR when the value is extracted from the object type. 

for eg. int a = 10;
 
 object o  = a; (implicit boxing no need to add any keyword for type conversion)
 
 o = 13;
 a = int(o);(Unboxing explicit conversion you need to add an additional int keyword to type cast that variable)

 Boxing is implicit and unboxing is explicit. 
 
-Method overloading - Method overloading is a way to implement polymorphism. its a type of polymorphism. IN method overloading u can create the same name 
method in a class but with the different method signature. method signature involves the no. of parameters, the sequence of them and the type of parameters but is does not 
include the return type of the method. for eg. 

class A{

void Display(int i){
COnsole.WriteLine(i);
}
void Display(int j, int i){
Console.WriteLine(j,i)
}
void Display(string i, string j, int k){
Console.WriteLine(i,j,k);
}}

all the three method's name is same but the different method signature but the return type of the methods is same. 

- Value type and reference type 

-abstract class and interface

-String in immutable if u want to do multiple operations on a string then use stringbuilder object and then 
covert that object to string. 

-compare 2 string objects in c#
Using ==
String.equals
string.compare

- Collections in c#
Collection provides a way
.net supports 2 types of collections. generic and non generic 

Non Generic      Generic 
Stack  -------->  Stack<T>
QUeue ----------> Queue<T> 
Sorted List -----> Sorted List<T>
Hash Table ------> dictionary<T>
Array List -------> list<T> 

Non generic - > Array List -> ArrayList is same as the array but it can contain the elements of different type and 
its size can be dynamic. it can be of any size. 

Hash Table -> hash table is same as of the array list but it contains the element in the key value pairs.

Sortedlist -> it is the combination of array list and hash table but it contains/represents the element in the
key value pair and in the sorted order. 

Stack -> stack contains the elements. 





JIT Compiler - Just in time compiler used to convert intermediate code into native code. and the compiler converts the code
into intermediate code. 

MSIL - Microsoft Intermediate Language

Managed Code and Unmanaged Code - Managed code managed by CLR. not managed by any entity.


how to setup a project

- Created a project
- Chose a Api controller without read/write actions 
- APi will always be of IActionResult return type like public async Task<IActionResult>
-IN the APi header we write [ProducesResponseType(StatusCodes.Status200Ok) and all the status which can api consume
- We did added the service and the repository file in the startup file in ConfigureServices method
- 



how to implement swagger in project ->

- Need to add Swagger in configure method 

1.  app.UseSwagger()
2.  app.UseSwaggerUi(c => {
c.SwaggerEndpoint("swagger/v1/swagger.json","testing_v1")
}); 

then need to add Swagger in ConfigureServices method too

3. services.AddSwaggerGen(c => {
      c.SwaggerDoc("v1", new OpenApiInfo {Title = "testing", Version = "v1"})});


# Stack and Heap 
there are 2 places the .net framework/core stores the items in memory as your code executes. these 2 are stack and heap. they both helps us to run our code. 

stack vs heap need to watch video 

using statement in c#
in c# all unmanaged code and class libraries must implement IDisposable or IAsyncDisposable interface for memory utilization. 
the using statement ensures the use of IDisposable and IAsyncDisposable interfaces. When the object's lifetime is limited to 
a single method then it is necessary to dispose that object after using the method. when we define any variable with using statement we can't 
update that variable means that is read only. and either the code runs successfully or get any exception in the method that object will get
disposed so it works as a try finally block. we can also declare one or more variables in a single using statement.

string message = 'hello how are you!';

using 

var reader = new StringReader(message);





difference between fromsqlraw and fromsqlinterpolated   -> fromsqlraw and fromsqlinterpolated both are the methods in the entity framework core and usedd to get the data 
from the database through the sql queries. they serves a similar purpose but there are some differences between them :

1. Query Building - 
FromSQLRaw -> this method allows you to execute raw sql queries by providing a raw sql string directly. you write a sql query string and sql executes it as it is. you need to ensure
that sql query is properly formatted and secure against sql injection. 

FromSqlInterpolated - This method allow you to build sql queries using interpolated strings. this means you can embed variables and expressions directly into the sql query making
it more type safe and less error prone compared to manually constructing sql strings. 

2. Type Safety
FromSQLRaw -> Since u provide the sql query as a simple string, so there's less type safety. you are responsible for ensuring that the sql query and result mapping are correct.
FromSqlInterpolated -> This method provides better type safety because you can use variables directly into the query. and EF core will generate the sql query with proper parameterization. 
This reduces the risk of sql injection and makes it easier to write queries without worrying about the sql syntax.

3. Readability and Maintainabliity -> 
FromSQLRaw -> raw sql queries can become complex and less readable when the sql string is long.
FromSqlInterpolated -> interpolated queries are more often more readble and maintainable, as they integrate c# code directly into the sql string, making it easier to understand 
the query's intent. 


What if we pass parameters into the fromsqlraw query? will compiler throws the error?
No, the C# compiler will not throw an error if you use string interpolation with FromSqlRaw. we can use string interpolation within a FromSqlRaw query because the
 method expects a string, and string interpolation results in a string. but we need to be cautious while using interpolation into the fromsqlraw becauuse the user can input any 
 variable and it can lead to the Sql injection vulnerabilities.

                       
3999  -> 1234567890 ->       
stock    moneyCapital ->    

axg services
: Different types of applications 
- Standalone applications - the applications which we need to download on our systems to run. like any gaming application, excel and google chrome. we need to download these applications
first before run them

- Web application - the application for which we don't need to download on our systems to run. like any online webapplication -> Gmail, facebook

# Programming Types: MOnolithic, Procedural, Object Oriented 

- Console Application -> that can be run in the command prompt. 

# Data types in c# 
value type, reference type and Pointer dataType

Value Type are further divided into 2 types -> System Defined/PReDefined DataType,  User Defined DataType
predefined DataType -> int, bool, char, float and userDefined -> Enumeratio…

.net mvc app

- what is MVC
- how to create model, controllers and views
- DbContext file
- how to read delete data from database using entity framework core(CRUD data using EFCore)
- Services
- View Components
- Authentication and Authorization
- Integrate Paypal for payments
- Dependency Injection
- Model Binding
- Routing
- Model Validation
- Tag Helpers



MVC -> model view controller

MOdel- for data intercations with the database we do use models.it contains the business logic.  

View- its a file which represents the user interface. its a .cshtml file. CS stands for C Sharp and HTML represents html code. from view u can trigger any request 
which will handle by controller.

Controller - it will get the requests and will handle those requests and will return the result to the view.its a C# class which inherits from the ControllerBase class. 


MVC Application ->  Created empty MVC application and then push to github added the github creds and pushed the repo to github

Folder structure -> Properties-> in launch settings file we can define the3 profile for the applciation. and all these profiles will be shown as option in the Run Command box(from 
where we run the project). 

wwwRoot section-> this is also known as the static file section. if u have any files that are static then you will keep those in the wwwroot section. 

Views -> for each controller we'll have a specific folder inside view folder.
we have a Error.cshtml file in Views folder which is getting used to show error if we have any error in the file. 
appSettings.json -> configuration file 

DbContext file -> to communicate the model with the database we need to have a dbContext file which understands the c# code. we can create a custom dbContext file by inheriting
the DbContext base class.

where we have many to many relation there we do use join tables concepts. 


----------------------------------------------------------------------------------------------------------------------------------------

MVC -> what is MVC -> MVC is an architectural software design pattern used to develop software applications in which we do have views to interact with. and based on these views some 
events occur which will handled by Controllers.
MVC is not only used for creating web based applications but its also used for creating mobile based applications and desktop applications where there we have a view/user
interaction associated/involved .

3 Components of MVC are : Model, View, Controller.

Model -> Model is the component which handles with the data. it used to fetch the data and to handle the business logic, it also handles the validations and other all the related 
things to database. it is used to interact with database where we have any kind of need of database we do use model.

View -> View is the component which interacts with the user interface. everything which user able to see on the UI handles by the views. Views files are of .cshtml extenstion.
.cs means cSharp and html represents HTML structure. any request view gets from thee user then view will interact with the controller and models to complete that need of 
the user.

Controller -> Controller is the last component of the MVC architecture. all the business logic are present in the controllers. controller gets the request from the views and 
then controller acts with the models(if required). controllers are the one which interacts with both model and views. 


ASP.net MVC -> ASP.net MVC is a web application development framework which follows the MVC design pattern which provides a clean seperation 
of code. and it was provided by microsoft. it was the most customizable and extensible framework provided by microsoft. 

NOTE -> so the point is MVC and asp.net MVC both are different. MVC is a architectural software design pattern whereas asp.net MVC is a web application development framework 
which based on the MVC pattern. 


what are model, view and controller from asp.net MVC point of view 
-> 	Mostly similar as of MVC pattern
 
-> difference between ASP.net MVC and ASP.net Web Forms

- Asp.net Web forms uses Page Controller pattern approach for rendering the layout whereas asp.net MVC uses Front controller approach for rendering the layout.in the case of 
page controller pattern approach, every aspx page has its own controller i.e code behind .aspx.cs file which is used to process the requests. whereas in asp.net MVC, a common 
controller is used for all the requests of all the pages.

ASP.net MVC is not going to replace asp.net web forms technique to create web applications. 

- 



Request flow for the asp.net mvc application  

- Client makes a request => Routing ENGINE will check if the incoming url exist or not in the route table -> if no url then will return a 404 HTTP status code to the client else
 if exist then it fetches the corresponding handler information and forwards the request to the controller and the action method in the controller. then the controller will do its
 action and will interact with model(if required) and after doing its work it will check the view to which we neeed to show on the UI.
 
What is View Model in ASP.net MVC



.asmx -> web services
.aspx -> represents web pages created using ASp.net web forms, a technology for building dynamic web applications.

what is ASP.NET MVC -> ASP.Net MVC is a web application development framework provided by microsoft that is based on the MVC architectual design pattern. It is an Open source
framework built on top of the .net framework to develop a web application that enables a clean code seperation. It is a complete alternative to ASP.net Webforms.  

ASP.NET MVC -> is a framework while MVC is an architectual design pattern. 

MVC -> MVC is an architectual design pattern which is used to developing interactive applications which includes the user interface. and based on the user interactions 
some actions are performed. it is not only used for web applications but also can create mobile applications and desktop applications where there is user interaction involved. 

MVC design pattern was introduced in 1970 that basically divides an application into 3 major parts: model, view and Controller. the main objective of the mvc design pattern is 
seperation of code, which means the business model and domain model are seperated from the user interface. 

Controller -> 
- A controller in asp.net mvc application is a class that is inherited from System.Web.Mvc.Controller. 
- the controller is the one that is going to be interact with the model and view both. 
- the controller class contains the public methods which are also called the action methods. these are the action methods which are going to handle the http requests. 
- in asp.net mvc, each controller class must ends with the word "Controller". 
- every controller must be located in the Controllers folder.


Views -> the view component contains the logic to represent the model data as a user interface with which the end user can interact. typically it creates the user interface with 
the data model provided to it by controllers. 

Models -> the models in asp.net mvc application are the componenets that contains a set of classes that are used to represent the business data as well as logic to manage the
business data. 

Routing in Asp.net mvc application -> Routing in asp.net app is a pattern matching mechanism that handles the incoming http requests and figure out what to do with that incoming
HTTP request.   the routing module is responsible for mapping the incoming browser request to a particular controller action method. 

WHen the client makes a request(http request), then that request is first received by the Routing engine. then routing engine figures out the URL pattern of the request and 
checks if that URL is present in the routetable or not. if present then it fetches the handler information and pass that request to the corresponding controller and action 
method. if there is not match found in the routing table , then it simply return a 404 HTTP status code. 

Different types of routing supported in mvc -> Convention Based Routing and Attribute Based Routing


in asp.net web forms -> we do use the mapping with the file name. each and every url shoould match with a specific .aspx file. 
for ex -> http://dotnettutorials/employeeinfo.aspx must match with a physical file i.e EmployeeInfo.aspx that contain necessary code and HTML for rendering the response to the
browser. so in asp.net webforms the URL pointing to the file must have its physical existence. 

theen asp.net framework introduced the concept of routing to eliminate the need of mapping each and every URL to a physical file.  the routing concept enables us to define the 
URL pattern that maps to a request handler. in case of asp.net webforms the request handler is a file(.aspx) and in the case of the asp.net mvc its a controller methods. 

QUE - What is a route in asp.net mvc applictions?
- the  route defines the url pattern and the handler information. the handler can be a physical file in case of webforms and can be a controller in the case of mvc application. 
in asp.net mvc application all the routes gets stored in the route table and then the routing engine uses this route table to determine the handler class for the incoming http 
request. 

Route Constraints -> route constraints are used to restrict the user to access the route for the specific constraints. we can add constraint on any route by using the 
routing methods. if we want to restrict that the route only takes numeric values in the route then we can specify the regular expression constraint while defining the route. 

Difference between routing and URL rewriting 
routing and url rewriting are very different since both looks similar. 
- URL rewriting mainly  focus on mapping one URL(new url) to another URL(old URL) while routing is focused on mapping a url to a resource i.e controller action method.
- URL rewriting rewrites your old url to new url while routing never rewrites your old url to new url.

Attribute Routing ->  if we are defining the routes by using [Route] attribute on the controller and the action methods then this is known as attribute routing. it provides you 
more control over the URL by defining routes directly on the actions and controller in the mvc application. 

the old routing i.e convention based routing is still fully supported by the mvc applications. in fact we can combine both the routing mechanism in the same mvc application. 

attribute based routing  comes in the .net mvc 5 but if we want to use  the attribute based routing in lower version than 5 we can also use that. for that we need to enable 
the attibute routing in the RouteConfig.cs file.  so Yes, both the convention and attribute based routing can be combined in a single mvc app. the controller action methods 
that have the Route attribute uses Attribute Routing and the action methods without the [Route] attribute uses convention based routing. 

Attribute based routing -> [Route("api/[Controller]/TransactionReadyToSend")]  or 
in admin app at the top before class Name
[Route("api/[Controller]/")]
[ApiController]

and on the method]
[HttpGet("Transactions")]

Advantages to use Attribute routing -> 
1. it gives us  more control over the URLs than connvention based routing. 
2. Reduces the chances for errors, if a route is modified incorrectly in RouteConfig.cs file then it may affect the entire application's routing. 
3. Easy to map 2 routes pointing to the same action. 


we can also specify the URl with the optional parameters by using ? in the route attribute like

[Route("MVCTest/{studentName ?}")] -> it means studentName is optional. if the url is MVCTest/ and MVCTest/Dhruv then both the URl will match with the route and performs the task. 

Default value can also pass to the parameters in the  route like

[Route("WebApiTest/{studentName = Dhruv}")] so in this case WebApiTest/ and WebApiTest/Dhruv both will match with the route. 

RoutePrefix in asp.net mvc -> route prefix is like if we have 3 action methods in the controller and all the routes are sharing the same url in the first like 
api/student then we can define the routePrefix on the top of the class with the [RoutePrefix("api/Student/")] then it will addd in all the 3 action methods route prefix this 
way we can avoid the rewriting of the duplicate route prefix in the endpoints. and in our web api's we do write [Route("api/[controller]/") like in admin b.e.


But what if we want to override this route prefix in our action method and we don't want to use the common route defined in the controller then ~ sign is used like 

[Route("~/tech/teachers")] now in this case it will not add the prefix and will render with /tech/teachers route. 


Route Constraints -> we can also add the constraints in the routes. suppose we have 2 methods in the controller and 1 is getting used to studetn details on the basis of id and other 
is used to get the details on the bassis of name then in that case we want that we specify the same route if in route there is int value then redirect to the id methods and string
then redirect to the name method then we can achieve it by using : like 

[RoutePrefix("Students")]

[Route("{studentId: int}")]  -> on the upside of the studetnId method

[Route("{studentName: alpha}")] -> on the upside of the studentName method and alpha represents to lower and uppercase alphabet characters.


HTML helpers -> as a developer in the asp.net webforms application, we generally use the toolbox for adding controls on any particular web page. but in mvc that is not 
avaiable we need to manually add the controls on the web page by using html. so for some ease, mvc provided some html helpers through which we can use different extensino methods
to create different HTML controls in a view. we can use those extension methods to create html controls programmaticalllly. 

like  if we use -> @Html.Textbox("firstname","Dhruv")

then at runtime the above textbox will generate the below code

<input it="firstName" name = "firstname type="text" value="Dhruv" /> so these are html helper methods.

is it possible to create our own html heloper methods -> yes

is it mandatory to use html helpers in asp.net mvc -> no

Html.Textbox helper method creates an element of <input type="text"> 

so like this we have different html helper methods for everything in html like for radio button and checkboxes.


------------

Action Selectors in mvc -> the actions are the methods in the controller which returns the response corresponding to the request. the action selecctors in the asp.net mvc are 
the attributes which can be applied to the action methods of a controller and are used to control which action method gets invoked in response to a particular request. 

types of actions selectors in mvc 
- ActionName
- ActionVerbs
- NonAction

ActionName -> it is used where we want to invoke an action method with a different name, than what is already given to that action method. 
suppose we have an endpoint in homeController like - 

public class HomeController: COntroller
{
 public string Index(){
 return "Index action method invoked";
 }
} 

now the above  method will get invoke by the /Home/index url but what if we want to invoke this method by using "/Home/List" then we would need to use the action method like 

public class HomeController: COntroller
{
 [ActionName("List")]
 public string Index(){
 return "Index action method invoked";
 }
} 
 
 now if u enter the url "Home/index" then will get an errror -> the resource cannot be found. 
 
 but now its returning a string then its ok. we don't need to change at any other place but what if its returning a view then its getting used in the view so we also need to 
 udpate at the view like 
 
 public class HomeController: COntroller
{
 [ActionName("List")]
 public string Index(){
  DataAccessElectronics DAE = new DataAccessElectronics();
  List<Product> ElectronicsList = DAE.GetDataElectronics();
  return View(ElectronicsList);
} 
}

now its returning a view and we have updated its route but in the view 

@{
    ViewBag.Title = "Index";
}

now run the application and navigate to Home/List it will throw the error whihc proves that it will search for a view with the name like List.cshtml, not index.html. 

so from an action method we can also return the vview name in the return view command which will tells that to which view this action method is attached like below:

 public class HomeController: COntroller
{
 [ActionName("List")]
 public string Index(){
  DataAccessElectronics DAE = new DataAccessElectronics();
  List<Product> ElectronicsList = DAE.GetDataElectronics();
  return View("index", ElectronicsList);
} 
}

now on rendering the Home/List it will check for the index view and the index view is already there and will return the view corresponding to it. 


2. Action Verb Selector -> we can also use the action verbs for any action method in the controller like [HttpGet] and [HttpPost] on the action methods then this way the 
action methods only will allow the http type calls. 

3. Non-Action selectors -> we do have some action methods in the controller which we don't want to call by someone. it is used to restrict access to the public method in the
controller. it indicates that the action method is not an action method. it is used when we want that method shouldn't be treated as an action method.


[NonAction]
public string Method2()
{
    return "<h1>Method 2 Invoked</h1>";
}



--------------------------

Data Annotation Attributes in ASP.net Mvc
- Adding annotations on the fields in the model like 

[Required(ErrorMessage = "FirstName is required")]
[StringLength(30)]
public string FirstName{get;set;}
+


[StringLength(30)]-> it will decide that the max length of the FirstName is 30 and we can also set the minimum length by this using

[StringLength(30, MinimumLength = 4, ErrorMessage = "First Name should be less than 30 chara")]

we can also add the regular expressions on the field in the model.

for the password type field we can use compare attribute, password type value attribute like below:

[DataType(DataType.Password)]
[Required(ErrorMessage = "Password is Required")]
public string Password
{
    get;
    set;
}
[DataType(DataType.Password)]
[Required(ErrorMessage = "Confirm Password is Required")]
[Compare("Password", ErrorMessage = "Password and Confirm Password do not match"]
public string ConfirmPassword
{
    get;
    set;
}


- Redirect result in asp.net mvc -> it is a type of returning response from an action method in the controller. if we want to redirect to any other url after the action method 
got executed then we can keep the RedirectResult return type of that action method like. if we want to redirect to "https://dotnettutorials.net" from the endpoint then simply 
use. 

public class HomeController : Controller
{
    public RedirectResult Index()
    {
        return Redirect("https://dotnettutorials.net");
    }
}

- RedirectToRoute -> if we want to redirect the user from one action method to another action method within the same controller or in the different controller then we do 
use the RedirectToRoute return type like:

public class HomeController : Controller
{
    public RedirectToRouteResult Index()
    {
        return RedirectToRoute(new { controller = "Home", action = "About" });
    }
}


- RedirectToAction -> The RedirectToAction result in mvc is resulting  the result to a specified controller and action method. Controller name is optional in redirectToAction method. 
if not mentioned the controller name the it will redirects to the mentioned action method in the current controller.  

public class HomeController : Controller
{
    public ActionResult Index()
    {
        return RedirectToAction("Login", "Account");
    }
}


Status Results in Asp.net MVC application
- HttpStatusCodeResult
- HttpUnauthorizedResult
- HttpNotFoundResult



VIEWS : 
	
Partial Views in Asp.net -> we need to develop a partial view when we need a common part of the user interfcae on multiple pages in a web applicaiton. 
a partial view is a regular view that can be used multiple times in an application and has the extension as .cshtml. and it is used for code reusability.

the partial views are the views that are rendered withing another view. the html output generated by the partial view is rendered into the calling view. like views, partial views
use the .cshtml file extension.

How can we call a partialView -> by 5 ways


- Html.RenderPartial
- Html.Partial
- Html.RenderAction
- Html.Action
- JQuery Load function


@model IEnumerable<PartialViewInMVC.Models.Product>
@{
    ViewBag.Title = "Index";
}
@Html.Partial("ProductDetails", Model)
<div class="open_grepper_editor" title="Edit & Save To Grepper"></div>


---------------------------------------
ASP.Net MVC Filters -> 

as of now, we discussed when  a client makes a request, then the request comes to the routing engine and routing engine navigates the request to  the 
controller and the specific action method handles that request and returns the response. But what if we need to run some code or logic before or after the action methods 
executes . if that is the requirement then we need to use the filters. the filters in asp.net mvc framework are the attribute  that allows us  to inject some logic or code 
which is going to be executed either before or after an action method  is invoked.

why do we need filters:
Caching, Logging, Error Handling, Authentication and Authorization etc . 


Different types of filters
1. Authentication Filters
2. Authorization Filters
3. Action Filters
4. Result Filters
5. Exception Filters

This is also the order of execution of filters if more than 1 filter is applied. but the point we need to remember is exception filter can be executed at any point in time when 
there is an unhandled exception that occurs in the application. 


Where can we configure the filters in ASP.net mvc> 
- Global Level(Applicable to all controllers and action methods)
- Controller Level(Applicable to all the action methods of the controller)
- Action Level(Applicable to that specific action)


1. Configuring filters at the global level -> if we want to configure the filters at the global level then in that case we need to define in the Application_Start method of 
the Global.asax.cs file as we know it is the first method which will get executed once the application starts. 

protected void Application_Start()
{
    FilterConfig.RegisterGlobalFilters(GlobalFilters.Filters);
}

2. Contoller level -> here u need to define the filter at the top of the controller. wehn you apply the filter at the controller level then it is applicable to all the 
action methods of the controller.

[Authorize(Roles = "Admin")]
public class AdminController : Controller
{
    //Code
}
3. Action level -> when u want to add the filter only on the specific action method of the controller then we can add the action level filters.

public class UserController : Controller
{
    [Authorize(Users = "User1,User2")]
    public ActionResult LinkToLogin(string provider)
    {
        // Code
        return View();
    }
}

Role and Responsibility of MVC filters -> 

1. Authentication Filter -> it is the filter which will be the first to be executed when we get any request. it willl be the one whihc runs before any other filter or action 
methods. this filter check the user from where we are getting the request is authenticated or not. the authenticated filters in mvc implements the IAuthenticationFilter interface.
the IAuthenticationFilter is used to create a custom authentication filter.  as of now there is no in build authentication filter provided in asp.net mvc framework. 

2. Authorization Filter -> it executes after the authentication filter. it is used to check if the authenticated  user has the right to access a particular resource or page.
The built-in AuthorizeAttribute and RequireHttpsAttribute are examples of  Authorization filters.

3. Action Filters -> these filters will run before the action method started to executed and after the action method executed. so if u want any logic to add before or after the
action method is executed then we can use action filter like if we want to change the arguments to the action method or if we want to change the response of the action method then 
can use the action filters.
the action filters implement the IActionFilter interface that has 2 methods. OnActionExecution and OnActionExecuted. if u want to add thee logic before the action methods executes
then u need to implement the onActionExecuting and if want to add any logic after the action method executed then need to use the OnActionExecuted method.

4.Result Filters -> the result filters in the mvc application are executed before or after generating the result of an action method. Action result type can be ViewResult, PartialViewInMVC
Result, RedirectToRouteResult, JsonResult which derives from the ActionResult abstract class.Result filters are called after the action filters. the in built OutputCacheAttribute
is an example of a Result filter. The result filter implements the IResultFilter interface which has 2 methods onResultExecuting and OnResultExecuted. if u want to add the logic 
before generating the result then u need to implement OnResultExecuting and if u want to add the logic after generating the result then need to use the OnResultExecuted.

5. Exception Filters -> the exception filters occur when there is any exception during the execution of the action methods of filters. the inbuilt HandleErrorAttribute is 
an example of the Exception filters. it implements the IExceptionFilter interface. 


How to implement the ErrorPage through Filters in ASP.net MVC app -> as we know through the Exception Filter we get the inbuilt HandleError attribute which is used 
to display the user friendly error page if we get any exception in the whole mvc app. because if we don't implement the error page and if any exception occurs then it is non 
user friendly. 

so first Create a Error.cshtml View 

Enable Custom Error in the web.config file 
- Need to add <customErrors mode=”On”></customErrors> in the <system.web> section of the web.config file in the mvc app.

Now apply the handleError Attribute in the application at the level on which u want to provide this error handling either at global level, controller or action level

Applying at controller level -> 

    [HandleError]
    public class HomeController : Controller
    {
        public ActionResult Index()
        {
            throw new Exception("Something went wrong");
            //return View();
        }
    }
	

now if u get any exception in this controller then u will see that view which we defined for the Error.cshtml file.

Applying globally -> need to define in the application_start method of the Global.asax file


we can also create the error page specific to the exceptions like null reference exception or divide by zero exception and for this need to define 2 different views and in the 
controller method  need to add:


[HandleError(ExceptionType = typeof(DivideByZeroException), View = "DivideByZero")]
[HandleError(ExceptionType = typeof(NullReferenceException), View = "NullReference")]
[HandleError]
public class HomeController : Controller
{
    public ActionResult Index()
    {
        throw new Exception("Something went wrong");
    }
    public ActionResult TestMethod1()
    {
        throw new NullReferenceException();
    }
    public ActionResult TestMethod2()
    {
        throw new DivideByZeroException();
    }
}
 	

- Custom Exception Filters 
what the need - the following things can't be achieved using the in built exception filter 
1. Cannot log the exception anywhere using the HandleError attribute.
2. It's not possible to handle the exceptions raised outside the controller.
3. Scenario based exception handling is not possible.


- Custom Error pages for the StatusCOdes -> we can also creates the custom error pages on the basis of status codes like if we want to return an error page on 404 and different on 
500 then first create the views corresponding to those status codes. then add the following lines in thhe web config file and then on getting the specific error u will get 
the corresponding error page. 

<customErrors mode="On" defaultRedirect="~/Error/GenericError">
  <error statusCode="404" redirect="~/Error/PageNotFoundError"/>
  <error statusCode="500" redirect="~/Error/InternalServerError"/>
  <error statusCode="401" redirect="~/Error/UnauthorizeddError"/>
</customErrors>

- ChildActionOnly Attribute -> suppose you have a scenario where you have one action method and you don’t want that action method to be invoked via URL rather you want that action 
method to be invoked by other actions of your application. Then in such scenarios, ChildActionOnly Attribute can be handy. So, when we decorate an action method with the
 ChildActionOnly attribute, then it is called child action in ASP.NET MVC Application and child action methods are only accessible by a child request.	
 
 --------------
- Caching -> to improve the performance of the app we need caching. for ex. if we have a page which shows the list of states that does not change frequently. then if we need this 
data then we need to call the api to get these states from database every time. so in these type of cases we can use caching and can improve the performance of the app. 

[OutputCache(Duration = 10)]
public ActionResult Index()
{
    System.Threading.Thread.Sleep(3000);
    return View(db.Employees.ToList());
} 

now if i navigate to the screen and then refresh the page then the state list is cached for 10 seconds and will show the data but after 10 seconds it will lost. 

Filter OVerrides -> [OverrideAuthorization] attribute -> if we applied the filter globally means on the whole app then it means the filter got applied to all the controllers 
and the action methods. but  what if we want to override taht filter for a specific action method then we can use the [OverrideAuthorization] filter on the action method.


Authentication and Authorization in ASP.net MVC ->
what is constructor

constructor is used to initialize the object of any class. it gets called when the object of the class gets created. 
these are the special type of methods of a class that gets executed when its object is created. the constructors in C# are responsible for object initialization and 
memory allocation of its class. 

for every class it  is mandatory to have the constructor without constructor we can't create an object of any class. but the question is if we don't create a constructor in any class
and if we create an instance of that class then we are successfully able to create the object of that class. How is that possible? it is possible because if we don't define any constructor
in any class then during compilation the compiler itself defines a default constructor for that class and all the data fields of that class will be initialised to the default values.


Points:
- The constructor name should be same of the class name.
- we can't add return type to constructor not even void. 
- It should not contain modifiers.
- In its logic return statement with any value is not allowed. 
- The constructor can have parameters. 
- It can have throw keywords it means we can throw an exception from the constructors.
- we can place the return; in constructor but not any value with the return keyword.


types of constructors

- Default Constructor   
- Parameterized constructor
- Copy Constructor
- Private Constructor
- Static Constructor

Default Constructor   -> default constructor are of 2 types
a) System Defined Default Constructor
b) User Defined Default Constructor

a) System dEfined default constructor -> if the programmer during the development is not defining any constructor then the compiler itself will provide a constructor at the time 
of compilation and that constructor will assign the default values to the datafields. but it will create only when the programmer will not define the constructor explicitly. 


when should the programmer define constructor explicitly -> when we want to add any logic during the time of object creation of any class then we should define it explicitly. 

b) User Defined Default Constructor -> the constructor which is defined by user without any parameters is known as user defined default constructors. this constructor does not 
accept any argument but we can write the logic inside the body. 

NOTE  -> the drawback of the default constructor is that all the objects of the class will have the same value as all of them and it is not possible to have all of the object 
have different values. 

if we want to create the objects dynamically then we should use the parameterized constructor. 


---- Parameterized constructor -> when any developer defines a constructor with the parameters is known as parameterized constructor. the advantage of this constructor is that 
we can assign the objects different values according to the parameters. 

----- Copy Constructor ->  when the developer defines a constructor of class type its known as copy constructor. we create this object to copy one object data into another object 
data. the main purpose of the copy constructor is to initialize a new object with the value of existing object. 

---- Static Constructor -> we can create a static constructor with the static keyword and the motive of the static constructor is that the this constructor will invoke only once
during the creation of 1st object of the class. no matter how many times the object will create but it will only invoke when the 1st object of the class will create. 

POINTS -> 
- only 1 static constructor can be created in a class.
- The static constructor should not have any parameter.
- it can only access the static members of the class.
- there should not be any access modifier in the static constructor definition.
- if a class is static then we can't create the object of that class.


------ Private Constructor -> We can define the private constructors in c# using private keyword. the constructor whose accessibility is private is known as private 
constructor. we do use this constructor so that the object of that class can't get create outside of the class. private constructor are used to create the object of the 
class inside the same class.

when do we use private constructor ->  when we want the caller of the class not to intiantiate the object of the class but only allow to use the class.

if any variable is declared as static then we can directly access that variable in any other class using className.variableName without creating the object of that class and
the same process followed by the constant variable. we can also access the constant variable directly by using the class Name.

Difference between static and non static constructor
if a class contains a static and a non static constructor then if we are creating the instance of that class. then first the static constructor will get called before creating the 
instance of that class and that instance will get created and then the non static constructor will get called.
and static constructor will get called only once whereas the non static constructor will get called every time when the object of that class will get created.

static constructor are implicitly called and non static constructors are explicitly called.
when the compiler defines a constructor implicitly then what kind of constructor will it be static or non static? -> it depends on the class if the class is static then it'll
define the static constructor else it will define nonstatic constructor.


PRivate constructor -> if u define a private constructor in the class then u can't create the object of that class in any other class but only u can create the instance of that
class in that class itself only, if u want to restrict the user to create the object of any class in any other class then u can define the private constructor in that class.

-------------------------
Destructors -> destructors are also called as Finalizers in C# are used to perform any necessary final clean up when a class instance is being collected by the garbage collector.
destructor is just same as the constructor with the same name as of the class but with a tilde ~ sign.  the constructor in the class is explicitly called when the object of the class
is created whereas the destructor of the class get implicitly called when the object of the class is destroyed.

the most important thing about a destructor is it can't have parameters so we can't overload the destructor in the class. 


when the destructor gets called -> destructor gets called automatically by the garbage collector when the object of the class is collected by the garbage collector.

when will the object of the class gets destroyed/ when will  the garbage collector run -> 

1. When the execution of the program is completed then the destructor will run.
2. The implicit calling of the garbage collector occurs sometimes in the middle of the program execution provided the memory is full so garbage collector will identify unused 
objects of the program and destroy them.
3. When we call the garbage collector explicitly by calling the Collect() method so that if there is any unused object then it will destroy those objects and will release the memory 
but its not a recommendable approach to call the garbage collector explicitly.

NOTE -> the most important point is that the destructor can only be defined in the classes. nowhere else. and the destructor can't take any modifier like public, private or protected. 


###########################

- Types of errors in c#
 Compile time error and Run time error
 
What is compile time error -> Compile time error occurs during the compilation phase. it is due to syntax errors or when the developer don't have the proper 
idea about the programming language. or when we assign any wrong value to a different data type. when we miss any parenthesis or double quotes or type wrong spelling 
for keywords.
These errors can be rectified by the developer and can be resolved before compiling the program.

HP Software ->
COM -> Component Object Model created by microsoft. through this model we can create window and web applications. disadvantages of COM are it is platform dependent it can 
run on only window OS. it does not follow all the OOPs concept. for window applications we do use VB and for web applications we use ASP.

- .net -> . refers to the object oriented and net refers to network . means through .net we can create object oriented internet applications. 

- Framework -> framework is a collection of many individual technologies which is used to create various applications. it is basicallly a software. 
 Framework provides 2 things BCL and CLR. 
 
- BCL -> BCL stands for Base Class Library. base class libraries are the building blocks of the programs of .net. without BCL we can't write the code. these are created by microsoft. 
 and when you installs the Framework it gets automatically with that framework.
 
- CLR -> CLR stands for Common Language Runtime. it's provided by the framework and its used to convert the intermediate code into the machine code. 

in .net code is compiled twice  by the following ways. 
for reference we have a program now for compilation first this program will gets converted into intermediate level code by the language compiler and then the CLR will 
convert that code into the machine code. 

NOTE -> Always 1st compilation is slow and the 2nd compilation is fast. 

JIT -> JIT stands for Just In Time compiler. its a component of CLR that is responsible for converting intermediate code to machine level code.

Different types of .net framework -> 

.net framework -> its the standard form of .net framework used to run applications only on windows OS.
.net mono framework -> its used to run the application on all the OS like linux, ubuntu and Ios. 
.net compact framework -> its a type which is used to run applications in smart phones or mobile phones.

what is exactly .net-> .net is a framework integrated with different technologies and used to create applications. 

Metadata -> data about data, metadata is used to define every type and member defined in our code in a multilanguage form. 

exe and dll -> exe stands for executable and dll stands for Dynamic Link library. exe files can be executed by itself but dll can't be execute by themselves. someone
needs to consume the dll files. when we compile any project then a .exe file will be generated and if we compile any class library then a .dll file gets generated which 
gets consumed by any other project. In .net framework both exe and dll are called assemblies. 

IEnumerable and List -> IEnumerable is an interface whereas List is a specific type of IEnumerable. We can iterate IEnumerable only through forEach loop but can iterate List
through various types. we can add or remove item from the list at any specific index but can't do that with IEnumerable collection. We can access a particular element in the 
list collection using index but can't access IEnumerable's. performance wise to iterate the IEnumerable is very fast than the List. 

Why is Class ABstract Data Type -> Any class specifies only its members and properties but don't give any idea/information about how they are implemented. that's make class 
abstract and its a user defined datatype that's why we can call it abstract data type.

difference between string keyword and System.String class -> Actually there is no difference between both. string keyword is an alias for System.String class. we can use anyone
we want.

Difference between System.text.StringBuilder and System.String -> the diff between them is stringbuilder objects are mutable but string objects are immutable. StringBuilder 
inherits from the System.Text class and string are present in System namespace.

int.Parse methods and int.TryParseInt() methods -> if we have a string "Hello" and on this string we want to know is it contains numberic values or not then if we do use int.TryParse
method then it will throws an exception but if we use int.TryParseInt() then it will returns false if the string does not contains string.

different types of properties available in c# -> Readonly, writeOnly, ReadWriteOnly

What is a static property -> property with the static keyword is known as Static property. this makes the property to available to callers without creating any instance 
of the class. we can directly access that property using class name without creating the instance of the class.

Virtual Property -> a property with the virtual keyword is known as virtual property. Virtual property can be override in the child class by using override keyword.

Abstract Property -> a property with the abstract keyword is known as abstract property. abstract property should not have implementation in its own class but in the child class
it should have the implementation.

NOTE -> C# is a strongly typed language.

DataTypes available in C# -> BuildIn Data Types and UserDefined DataTypes

BuiltIn DataTypes -> which are already defined in language -> int, float,char, double,bool

UserDefined -> we can define userDefined dataTypes using struct,class, interface,enums

Difference between int and int32 -> int and Int32 both  are synonyms they are same nothing different.

2 types of datatypes available in c# -> Value Type and Reference Type -> 

If u define a userDefined datatype using struct keyword then is it value type or reference type -> its value type

if u define a userdefined datatype using class keyword then is it value type or reference type -> its reference type

are value type sealed -> yes

what is the baseClass from all the value type variables are derived -> System.ValueType


Value type datatypes -> struct and enum

reference type datatype -> class, interface, arrays, delegate

value type and reference type -> value types are stored on the stack whereas referencetype are stored on the managed heap. value type are stored on stack that's why there is not 
headache of garbage collection but we do need memory allocation and garbage collection for reference type variabels.
value type directly holds their value but reference types varaible stores the reference of the memory location where the actual object is stored.

casting a datatype -> to convert the one type of data into another type of data is known as type casting. type casting is of 2 Types 
Implicit Conversion, Explicit Conversion

Implicit Converstion -> its a type of casting where we don't need to specify any external type casting. no special syntax is required. example includes
conversion from smaller datatype to larger datatype and conversion from child class to parent class.

Explicit conversion -> its a type of casting where we need to do the casting explicitly. there may be a risk of data loss when u convert a larger datatype to a smaller datatype 
then we need to explicitly define the cast operator.

Explicit conversion requires a cast operator whereas implicit does not requires. explicit converstion can lead to a data loss but implicit does not.

IF casting fails what type of exception we will get -> InvalidCastException

Boxing and Unboxing -> to convert the value type into reference type is known as boxing and to convert the reference type into value type is known as Unboxing

int i = 100;
object j = object(i);   ----------------> boxing 

object i = new Object();
int i = int(i);           -----------------------> Unboxing

Access Modifiers in C# -> Public, Private, Protected, Internal, Protected Internal



PUblic -> Public type or member can be accessed by any other class anywhere in the same assembly or 
in any other assembly that references it.

Private -> private type or member can only accessed in the same class or struct.

protected -> protected can only be accessed in the same class or struct or in the derived class.

internal -> can only be accessed in the same assembly but not from another assembly.

internal protected -> can be accessed in the same assembly or by any other derived class in another assembly..

why do we use access modifiers -> to control the accessibility of methods/properties in the codebase.

Can derived classes have greater accessibility than the base class -> no it will throw a compile time error. 

what is the default access modifier for a class, interface, struct declared directly with a namespace -> internal

Can we specify the access modifier for an interface member -> NO we can't specify the access modifier for an interface member because they are by default public. that's why 
we don't specify any access modifier when we define the service method inside the service interface.

can u specify an access modifier for an enumeration -> no we can't because they too are public by default..

4 pillars of OOPs -> inheritance, polymorphism, Data Abstraction and Encapsulation

we have class and structs -> classes supports inheritance but structs does not supports inheritance.

difference between interface and abstract classes -> 
1. we can define the methods in the abstract classes but in interface there will be no implementation of the methods.
2. we can have access modifiers in the abstract classes but in interface we can't have those access modifiers because they are by default public.
3. interface can inherit from interface only but an abstract class can inherit from an abstract class and an interface too.
4. an interface can inherit from the multiple interfaces at the same time but an abstract class can't be inherit from the multiple classes.

difference between class inheritance and interface inheritance

classes and structs can inherit from multiple interfaces at the same time but not from the multiple classess.
when classes and structs inherits the interfaces then they inherit only the method names and signatures because interfaces only includes the 
method definition not declaration.

Can u create an instance of an interface -> no we can't.

when a class inherits an interface then what are the 2 options available for that class.
1. Provide implementation for all the members interited from the interface.
2. if the class does not wish to provide implementation of the interface methods then declare the class as abstract.
 
like in our projects if StudentService is inheriting IStudentService then we should provide the implementation of 
all the IStudentService methods in the StudentService file.


-------------------------------------

- What is an abstract class in C#
A class that is declared using the keyword abstract is known as Abstract class. an abstract class is a partially implemented class used for implementing some of the operations
which are common for all next level subclasses. so it contains both abstract and not abstract properties, variables.

An abstract class may or may not have abstract methods. but if a class contains an abstract method then the class  should be declared as abstract. the abstract class cannot be
instantiated directly means we can't create an object of the abstract class. its compulsory to create a new class from an abstract class in order to provide the 
functionality to its abstract functions.

Can u create an instance of any abstract class if not then why?  -> No we can't create an instance of an abstract class.because in abstract class we don't have the implementation of 
the methods we just have the definition of the methods. so if we create an instance of that class and access any method then it will throw the error. so that's why we can't create
the instance of an abstract class.

what is a sealed class ->  where we do use the sealed keyword with the class name that class is known as sealed class. if we want any class can't be inherit by any other class
then we do use the sealed class. 	

what is the abstract method -> a method that does not have the body is known as abstract method. it is declared with the modifier abstract. it contains only the signature and
does not contain the body of the method. an abstract method should be terminated with a semicolon. overriding  of an abstract method is compulsary.

can a sealed class be used as a base class -> no 

what is the diffference between private and sealed method in c# -> we can't inherit the private method but sealed method can be inherited but can't override. so we can not call the 
private methods from the child class but the sealed method can be called from the child class. the same private method can be defined in the child class and it does not lead to 
compile time error.

when should a class be declared as sealed -> if we don't want to override all the methods of our class in sub class.
if we don't want to inherit any class.

difference betweeen method overriding and abstract methods in c# 
- the concept of the overriding and abstract methods is same because in both the cases we would override the methods in the child class but the only difference is that 
in the case of method overriding it is not compulsary to overridde the method in the child class but in abstract method its compulsary to override the method in the child class.



How to configure swagger in your app?
firstly add the below configurations in the request pipeline 

app.UseSwagger();
app.UseSwaggerUI();

and add the configuration in the services 

builder.services.AddSwaggerGen();

now through this code your swagger will be configured.

now if we want the swagger will open at the / route also then we need to add 

app.UseSwaggerUI(x => {
x.SwaggerEndpoint("./swagger/v1/swagger.json, "v1");
x.RoutePrefix = string.empty;
})


To add the JWT Authentication need to add the authentication in app

builder.services.AddAuthentication(sharedOptions => {sharedOptions.DefaultScheme = "Azure AD"}).AddJwtBearer(options => options.Authority = instance + tenantId;
options.TokenValidationParameters = new TokenValidationParameters(){
ValidIssuer =  issuer,
ValidAudience = audience
});


and need to update the services.AddSwaggerGen function in the configureServices method.

services.AddSwaggerGen(c => 
var securitySchema = new OpenApiSecurityScheme{
Description = "Using the authorization   header with the bearer scheme;
Name = "Authorization",
In = ParameterLocation.Header, 
Type = SecuritySchemeType.Http, 
Scheme = "bearer",
Reference = new OpenApiReference{
Type = ReferenceType.SEcurityScheme,
Id="Bearer"
}
};

c.AddSecurityDefinition("Bearer", securitySchema);
c.AddSecurityRequirement(new OpenApiSecurityRequirement{

{securitySchema, new [] {"Bearer"}}
});
)








services.AddSwaggerGen(c => c.AddSecurityDefinition("Bearer", securityScheme);
c.AddSecurityRequirement(new OpenApiSecurityRequirement{

}

Polymorphism -> Polymorphism is the main pillars of the OOPS. it gives us the ability to use the same method in the child class too.
through this we can override a method in the child class by using override keyword but that function should be virtual in the parent class. poly means many and phism 
means forms. it can be achieved by  3 types:

method overloading, overriding and method hiding

Method Overloading -> its again of 3 types :->method overloading, operator overloading and Constructor overloading

types of polymorphism ->  compile time polymorphism and run time polymorphism

Compile time polymorphism -> in this polymorphism, the object of the class recognizes at the time of compilation which method to be executed for a particular method call and 
binds the method call with method definition. this happens in the case of method overloading becuase in the case of mehtod overloading we have same functions but have different 
signatures so compiler first now which method is being called ont he basis of arguments passed. it is called static polymorphism. it can be achieved by method overloading and operator 
overloading.

Run Time polymorphism -> in the run time polymorphism we can't find which method to be call at compile time. the object of the class will find out at run time to which method
it needs to bind because in this all the methods have the same signatures. so it is also known as late binding. 


Different types of overloading - function , operator, constructor

Function Overloading -> function overloading and method overloading both are same. when we declare a method with the same name which present in the class already then its called
method overloading. for method overloading the method signatures should be different but the name of the method should be same. method signatures includes no. of parameters, type 
of parameters. it does not include return type of the method. function overloadin can be done in the same class or in the child class. 

When should we overload methods -> to execute the same logic ex addition or subtraction with the different no. of parameters and different type of parameters then we should use 
the method  overloading.

what is inheritance based overloading -> when we declare the same method in the child class which is declared in the base class then its called inheritance overloading. 

what is funciton/method overriding -> Redefining the same super class method in the child class method is known as method overriding in this case the method name and signatures 
all should be the same in both the classes. in this we define the base class function as virtual so that it can be override in the child class and in the child class we use 
override keyword to override that method. it cant be  done in the same class if we do so we'll get a compile time error.

when do we use method overriding -> when the base class method implementation is not completing our requirements then we do override the method in the child class. 
Overrding the base class method is not compulsary in the child class. it is not mendatory that we'll override the method in the child class. 

how can we execute the parent class method if it is  overriden in the child class -> after re-implementing the base class method in the child class the object of the child class
will call its own method but still if  we want to execute the parent class method then we can create the instance of  parent class in child class and can invoke through that or 
we can call that by using the base keyword.

Difference between method  overloading and overriding

in method overloading the method signatures should be different but in overiding it should be same.
method overloading can be done in the parent and base class both but overriding can be done only in the child class.
its an approach to define the same method with the same name but different signature whereas overriding is to define the same funciton with same name and same parameters.
to overload a parent class function it does not require any permission from the parent class but for overriding we need permission from parent class to define that funciton as virtual.
Overloading is all about defining multiple behaviours for a method whereas overriding is all about changing the behaviour of the funciton.
overloading used to implement static/Compile time polymorphism and overriding used to immplement runtime/dynamic polymorphism.
no seperate keyword are used for overloading but for overriding virtual and override keyword gets used.

What is method hiding.
method hiding is an another approach to use the base class method in the child class. in this if we don't want to override the base class method and want to use the same method 
name in the child class then it is method hidning. we need to use new keyword for that. in method overriding we need permission from the base class but in hiding ew don't need 
any permission. if the function is not defined as virtual then also we can use that method by using new keyword.

it is not mandatory to use the new keyword it just denotes that the method hiding is taking place here.



what the difference between method overriding and method hiding

through method overriding we can only reimplement the virtual method by using override keyword in the child class but by method hiding we can reimplement the methods 
which are not declared as virtual in the parent class by using new keywords. it is optional to use the new keyword in the method hiding but if we are not using then will get a
warning 'if hiding is intended then use new keyword'.

How can we call the parent class method in child class?
2 ways either by creating the parent class object or by using the base keyword.

Partial Class -> A class whose definition is present in 2 or more files is known as Partial Class. all of the parts of the partial class gets combined at the time of 
compilation. it is mandatory to have partial keyword in the class definition.
Key Points -> 
- all the parts must have the partial keyword.
- the final class is the combination of all the parts at compile time.
- all the parts must be available at the time of compilation to form the final class.
- all the parts must use the same access modifier.
- any class members declared in a partial definition are available to all the other parts.

advantages of using partial class-> multiple devs can do work simultaneously. if we have a big project then this can be follow.

- is it possible to create partial structs, methods and interfaces in c#.
yes we can do that the same way of classes.

- can we create delegates and enumerations as partial>
no 

can different parts of a partial class can inherit from different interfaces ->>>>>>>...  yes 


can we create nested classes as partial classes? -------> yes 

points to keep in mind while creating partial methods -> 
- partial method declarations must begin with the partial keyword.
- the return type of the partial methods must be void.
- the partial methods are implicitly private and they can't be virtual.
- the partial method should be in the partial class if the class which contains partial method is not partial then will get compile error.
- the parameters of the partial methods should be same.
- In a single class a partial method can be defined only once. we can't define the same partial method in the same class more than once.

if u do not specify an access modifier for a methods, what is the default access modifier> ->....... private 

what is a nested type in c# --> 
a type(class or struct) defined inside the  other class is known as nested type. 


points to note about partial methods ->

Delegates -> 

we can call a class function by 2 ways 
 1st is to create the object of the class and then call the funciton by that object and 2nd is by class name this can be  done by using delegates.
 
 Before calling the class function by using a delegate we must need to define the delegate. delegate are user defined type safe functions which call the function of the class.
the signature of the delegate must match with the signature of the function to which we call. 
 we need to pass the function name in the delegates while calling any function . they are of 2 types 
 
- Single cast delegate ->>>>>. where we can call a single function 
- Multi Cast delegate ->>>. where we can call multiple functions 


DELEGATE SYNTAX ->>>. TIPS TO REMEMBER DELEGATE SYNTAX -> a delegate syntax is very much similar to a function with a keyword delegate 

eg.  for a single cast delegate 

namespace demo{
//here we are definining delegate outside the classs
public delegate void HelloFunctionDelegate(string message);
class Program{

public static void main(){

// creating delegate object by passing function name in the constructor
HelloFunctionDelegate hello = new HelloFunctionDelegate(HELLLL);
hello("Print This");
Console.ReadLine();

}

public static void HELLLL(string message){

Console.WriteLine(message);

}
}
} 


 - > Multicast delegate -> its a delegate that has reference to more than one function. all the functions will get called when we call multicast delegate.
 
 eg : multicast delegate
 
namespace demo{
public delegate void multiCastDelegate();

public class demo{
public static void main(){
multiCastDelegate delegate1 = new multiCastDelegate();
multiCastDelegate delegate2 = new multiCastDelegate();
multiCastDelegate delegate3 = new multiCastDelegate();

multiCastDelegate delegate4 = delegate1+ delegate2 + delegate3 - delegate2;

delegate4();


public static void SampleMethodOne(){
Console.WriteLine('first');
}
public static void SampleMethodTwo(){
Console.WriteLine('second');
}
public static void SampleMethodThree(){
Console.WriteLine('third');
}
}

}

explain the properties of exception class -> exception class has 3 properties

- Messsage - This property will store the reason wwhy the exception has occured.
- Source - this property will store the name of the source by which the exception has occured.
- Helplink - This is used to provide a link to any file/URl to give helpful information to the user when an exception is raised.

multiple catch blocks in c# -> we can write multiple catch blocks to a try block but it is mandatory that only the 1 catch block will get executed.

1 thing we should always keep in mind that if we are defining multiple catch blocks in a single try block then we should never put the 1st catch block as below:

catch(Exception ex)
because the above block will catch all the exceptions and the remining catch blocks will never get executed so we should keep this block in the end.

Finally Block in C# -> if we are not using the catch block with try and any exception occur then will the finally block gets execute or not? yes 

why do we need finally block -> whenver we want the resource release logic then we would need this finally block it is mainly used for memory releasing.to release the variables
declared in the try and catch blocks.

in how many ways we can use try, catch and finallly blocks:

1. try, catch and finally.
2. try and catch
3. try and finally


Types of exception -> System Exception, Application Exception

System Exception -> caused by the CLR.  ex -> null reference exception, indexOutOfRangeException
Application exception -> caused by the programmer eg -> UserDefined exception

why do we need Custom/user Defined Exception -> when our requirements are not fulfilling OR if we want to throw the exception for a particular case.

How to create own Custom Exception class in C# -> public class OddNumberException: Exception

Inner Exception in C# -> the inner excpetion is a property of  the exception class.if u go to the definition of the exception class then u will find its a readonly  property
 of the exception class. that;s why it's present in all the child classes and even in the userDefined/Custom Exception classes.
 
 This property gets the exception instance that caused the current exception.it returns an object that describes the error that caused the current exception.
 
Eg of inner exception -> if we get any DivideByZeroException in the try block and it catched by the catch block and in the catch block we have code to write that exception to a file
but while writing to that file we again get an exception FilenotFoundException then we will get the FilenotFoundException in the outermost catch block but what about the actual DivideByZeroException will we get
that or not. yes we get that in the innnerException of that exception.

Collections in C#

Arrays -> as we know we have variables to store the values in any of  the programming language. and these variables are used to store only 1 value. but what if we have multiple
values then will we create multiple variables for all the  values? the answer is no. we can simply create an array to store all the value at 1 place. we can overcome this problem 
by using arrays.	

the arrays is defined as a collection of similar data elements. if u have some sets of integers then we can simply create an array and use that array to store all those 
integers. Ways to declare an array in C#. we can define the array by 2 ways. 

- First is initialize the array.
- Second is intialize and define the array elements at the same time

1. int[] array1 = new int[5]; -> in square brackets the size of the arrays
2. int [] array1 = {1,2,3,4,5};

array is of 2 types. 
Single dimensional array -> in which we do have only rows. the data is arranged in the form of the rows.
Multi Dimensional array -> in which the data is arranged in the form of rows and columns. and multi dimensional array is again of 2 types.

1. Jagged Array -> Whose rows and columns are not equal.
2. Rectangular Array -> Whose rows and columns are equal.

we can access the elements of array using the index of the array. and array index starts from 0.

if we are creating an array using int[] array1 = new int[5];
 then we can define the elements of the arry using -> array1[0] = 2;
 array1[1] = 9; and so on.
 
Can we use forEach loop to iterate through the arry-> yes because the array is derived from the SYstem.Array class which implements the IEnumerable class.


Single D array -> int[] arr = new int[6]; or int[] arr = {1,2,3,4,5};

Array methods-> Sort, Reverse, Copy, Length,GetLength

Implicitly Typed Arrays -> When we declare an array using the var keyword  then such arrays are known as Implicitly typed array.
eg. var arr = new[]{1,2,3,4,5};


MultiDimensional Array -> 2 D array
1. Rectangular arry -> in which  row and columns are equal. 

eg. int[] arr = new int[i, j]; ith row and jth columns

int[,] arr = new int[3, 4];

  0 1 2 3 
0  
1
2

how to initialize 2d array ->   int[,] arr = {{2,5,9},{1,2,3,4}}

now to iterate the 2d array we required a nested loop -> one for loop for accessing rows and one for loop for accessing columns


Jagged arrays in C# -> there are 2 d array which also stores the value in row and columns. but here in the jagged array  the column size will differ from row to row. 
if in the 2nd row we have 4 elements then in the 3rd row we can have 5 elements in the next row we can have 9 elements. so where the elements gets differ according to row that 
is jagged array and where we get the fixed column in every row then that will be a rectangular array.

limitation of array ->  array is of fixed length we need to define the array length while initializing. if we store more elements than the size of the array then the elements 
can be loose. we can't increase the size of the array once declared.


--------------------------------------
-> Collections in C# ->  Collections are nothing but the groups of elements like a collection of employees, collection of books.

general categories of Collections are of 4 types -> 
1. Indexed Based -> array, List
2. Key Value Pair -> Hashtable, SortedList
3. Priortized Collection -> Stack, Queue
4. Specialized Collection -> String Collection, Hybrid Dictionaries

1. Indexed Based Collection -> in the collection in which we can find the element on the basis of index.
2. Key Value Pair Collection -> In which the data gets stored in the form of key value and through the key we can access the value of the element. like Hashtable, SortedList, Dictionaries
3. Priortized collection -> it helps u to find an element in a particular sequence.eg. FIFO, LIFO 
4. Specialized collection -> they are designed for special purpose. 

Collection are classes that represents a group of objects. we can say a collection is a dynamic array. that means the collection in c# have the capability of storing multiple 
values but with the following features.
- Size can be increased dynamically.
- we can insert an element into the  middle of the collection.
- it also provides the facility to remove or add element into the middle of the collection.

Collections are of 3 types:
1. System.Collections.Generic
2. System.Collection   -> non generic collection
3. System.Collections.Concurrent

Non Generic collections (System.Collection) -> these are defined under the System.Collection namespace. the non generic collection classes in c# operate on objects. and can handle 
any type of data, but not in a safe type manner.



ArrayList -> ArrayLisst is a non generic collection class that acts an an array but provides the facility such as dynamic resizing, adding and deleting elements from the middle 
of a collecction. i.e when we don't know the data then we do use ArrayList.
It is used to create  a dynamic array whose size is not fixed.there is no need to specify the size of the arrayList. we can add the data of the same type or of different type.

Properties of Arraylist in C# -> 
1. the element can add or removed from the arrayList  collection at any point of time.
2. the arraylist is not guaranteed to be sorted.
3. elements in the collection can be accessed using an integer index.
4. it allows duplicate elements.

ArrayList arraylist = new ArrayList();

how to add elements in arraylist => arrayList.Add(5);, arrayList.Add("dhruv"); arrayList.Add(89);

how to iterate an arryList -> using foreach loop 
how to insert elements in an arrayList at a specific location -> arrayList.Insert(index,value) -> arrayList.Insert(2,56);

how to remove elements from arrayList -> arrayList.Remove(5);, arrayList.RemoveAt(2);  
arrayList.RemoveRange(int index, int count);

---------------------> Difference between array and arrayList   

Array -
fixed Length, can't insert or delete from middle, type safe only 1 type of value can store, Boxing and unboxing are not required.

ArrayList ->
variable length, insert or delete in the middel possible, not type safe any type of value can store, boxing and unboxing are required.


---------------------------------------
HashTable Collection class in C# -> the hashtable is a non generic colleciton in c# that stores the elements in the form of key value pair. the data in the hashtable is organized 
on the hash code of the key. the key in the hashtable will be defined by us and more importantly that can be of any data type.once we created the  hashtable  collection we can 
access the elements by using the key. 

Characterstics -> it stores the elements in the form of key value pair.
- hashtable class belongs to System.Collections namespace.
- it implements the IDictionary interface.
- the keys can be of any datatype.
- the keys should be unique and can't null.
- we can access the value by u…

async await ->  wherever we want to use  asynchronous programming we need to use async await keywords. for  those async operations for which we don't want to block the main thread.
so when we are using the await keywords in the function then we are freeing the thread which is executing this function. we are telling the thread just do any other work instead of 
waiting for the promise/result. 

for eg: 

public static void main(string args[]){
Console.WriteLine("main method started")
SomeMethod();
}

public static void SomeMethod(){
Console.WriteLine("Some method  started");
Thread.Sleep(TimeSpan.FromSeconds(10));
}

now in the above  example the main method will gets called the the first console main method started will console now it will call the SomeMethood function and in that function 
the thread will get on sleep for 10 seconds then in this procedure the thread will get blocked for 10 seconds and the COnsole will get freeze. now we can have any other command
too instead of thread sleep command we can have any database operation which takes some time. so what can we do now we can use asynchronous programming to avoid the blocking 
of the thread.

like 

public async<Task> static void SomeMethod(){
await Task.Delay(TimeSpan.FromSeconds(10);
}

it is important to understand that the await keyword is not asking to thread stop for the 10 seconds but its saying thread to do any other work until 10 seconds/we get our task 
done. 

--- Task Class in C# -> 

whenever we do use  async function then we want to return Task, Task<T> from the function. Task is a promise that the operation to be performed not immediately but sometimes in future.

difference between Task and Task<T>
- Task is used wherever we are using await in the function and we are not returning any value from the function and Task<T> is using there we are returning a particular type of 
value. if our asynchronous function is not returning anything then instead of using void we can simply using Task.


---------

Difference between Multithreading, Parallel Programming, Asyncronous Programming

Multithreading -> This is all about a single process split into multiple threads.
Parallel Programming -> This is all about multiple tasks running on multiple cores simultaneously.
Asynchronous Programming -> This is all about  a single thread initiating multiple tasks without waiting for each to complete.

what's the role of configureServices and Configure method in C#
- ConfigureServices method is optional in startup file and all the services of the project we add in this method. ConfigureServices method is getting called before the configure 
method.
- COnfigure method is used to add all the middleware components in the IApplicationBuilder instance which presents in the configure method. COnfigure method also specifies how the 
application will react to different requests. the app.use method is used to add the middleware in the application. we can add the middleware in the CreateHostBuilder method of
program.cs class instead of defining them here.

- Request Processing Pipeline process in asp.net projects

Middleware is a software that assembles into the pipeline of the  app that handles the requests and responses. each component 
-Chooses whether to pass the request to next component in the pipeline

Request delegates are used to build the request pipeline of the app. and they handle each HTTP requests.
request delegates are configured using the use, run, map extension methods. app.use is used to add the middleware delegate in the  pipeline. when u want to pass the context to the 
next middleware then use app.use extension method. app.run adds a terminal middleware in the pipeline. When you want to terminate the pipeline then prefer the app.Run method.

if u are adding codebase of app.use to add any middleware in your pipeline after the app.Run method then it will not added to your  request pipeline because app.run terminated
the process of adding middleware in the pipeline.


----- Explain the middleware in the asp.net core?
Middleware are the components which added to the request pipeline of your app which will handle all the request and responses in the app.and either transfer the request to the next
middleware or not. when a middleware component terminates  the request then its known as Terminal Middleware. so these are responsible for the HTTP requests and their response.
by using app.use method we add the middleware in the pipeline.

Request Delegate -> request delegates are used to build the request pipeline of the app and they handles each HTTP request. they can be configured using use, run and map methods.

- How routing works in asp.net core?
routing is responsible for matching incoming HTTP request and dispatching these requests to the app's executable endpoints.


REST VS SOAP

Rest and Soap are 2 difference approaches to online data transmission. specifically both defines how to create API's, which allow data to be communicated between web 
applications. REST(Representational State Transfer) is a set of Architectural principles. SOAP(Simple Object Access Protocol) is an official Protocol maintained by the World Wide 
Web Consortium.(W3C). The main difference between them is SOAP is a protocol whereas REST is not.Typically an api will adhere to one of them either SOAP or REST.


REST -> REst is a set of Architectural principles which is used to create API's for lightweight web applications and mobile applications. because its a set of guidelines it leaves 
on the developers to follow these set of principles while creating API.
When a request of data is sent to API it is usually sent by the HTTP. Once a request is received the API will return the response in the form of JSON, XML or any other format. but 
REST API's JSON is preferred as it is easily human readable and widely accepted.
Rest api's are lightweight as there is not built-in security and transactions compliance.

An application is said to be RESTful if it follows the below 6 architectural guidelines. 
- A Client Server architecture composed of client, server and resources.
- Stateless Client Server communication means no client content is stored on the server between requests.
- Cacheable data to eliminate the need for some client-server interactions. -> cache the data which is not changing frequently like list of states

SOAP -> Simple Object Access Protocol

SOAP is a standard protocol designed first so that applications built with different languages and on different platforms can communicate easily. because it is a protocol so it 
has a set of rules that increases its complexity and overhead, which can lead to longer page load times. however these standards also offer some built-in compliances that makes it
preferable for enterprise scenarios. the built in standards include ACID properties -> atomicity, consistency, isolation and Durability, which is a set of properties  for ensuring 
reliable database transactions.

when a request to send an api it can be handled by any of the protocols HTTP, SMTP, TCP etc. however once a request is received, api will return SOAP messages which is machine 
and human readable form. A completed request to an api is not cacheable in SOAP so it can't be accessed later without sending a request to api again. 


what's the difference between MVC and web api?
-ASP.net mvc is a framework to create web apps and API's using MVC architecture. when u are inheriting/driving your api controller class from Controller class then it
adds the support to views but when u want to create web api then u drive your api class from ControllerBase class which don't give u the ability for returning views from endpoints.

What is asp.net web api?
- ASP stands for Active Server Pages. ASP.net is an updated version of legacy ASP. it is a framework used for developing HTTP services to provide response to client requests.
it can be accessed in different applications on different platforms.it is very easy to develop HTTP services using ASP.net Web API.
it can be used by different clients:
- Desktop Applications -Mobile Applications -IOTs -Browsers 

-- Advantages of using Asp.net web api's
- It provides the best platform for developing restful applicatoins on .net framework.
- It completely supports routing.
- It provides enough flexibility in web api's creation.

-- use of HTTPResponseMessage?
-Used to set response values such as header and status control. it simply allow us to work with HTTP Protocol. it represents HTTP response messages that contains data and statusCode.

- Difference between APiController and Controller?
 ApiController - Used to return data that is arranged in series and then sent to the client.
Controller - used to provide normal views.

- What do u mean by caching and what are its types?
Caching is the process to store the data for future requests. the cache is a temporary storage area.Cache keeps all frequently or recently accessed files or data in the cache memory
and access that data from the cache memory itself rather than actual address of data or files.
Advantages : 
- it is considered the best solution to ensure that data is served where it is needed to be served that too at a high level of efficiency which is good for both client and server.
- it delivers web object faster to the end user.
- it reduces load time to the server. and decreases network costs.

Types of Caching: Page Caching, Data Caching, Fragment Caching


- WCF is replaced by ASP.NET web api. is it true?
No, WCF was developed to develop SOAP-based services and ASP.NET is used to develop non SOAP based services.WCF is still considered a best way if one has their services using HTTP 
as the transport and they want to move some other transport like TCP, NetTCP etc.

WCF - It is a framework used to develop SOAP based services. It also supports various transport protocol.
ASP.NET WEB API -> It is a framework used for developing non-SOAP based services. it is limited to HTTP based services.


- What are the main return type  supported in ASP.NET WEB API/
IHTTPActionREsult, HTTPResponseMessage, VOId, Other types like int, string,bool etc.

- What is ASP.nET web api routing?
Routing is the most important part of the ASP.NET web api. it tells which action we need to do for a specific request. its a new way how Web api matches a URI to an action.
Controller is basically a class containing various actions and routing tells us which action we need to call in a controller. Whenever a web api framework receives a request, it 
routes that request to the action.

there are 2 ways to do the routing in our application. 
Convention Based Routing, Attribute Based Routing.

Convention Based Routing -> Web Api supports convention based routing. in this type of routing, Web API uses route templates to select which controller and action method to execute.

Attribute Based Routing -> web api 2 generally supports a new type of routing known as attribute routing. as the name suggests, it uses attributes to define routes. it is the ability 
to add routes to the route table via attributes.

Convention -> on the basis of controller name automatically calls the controller action
Attribute -> define the route on the api's like in our admin app

- How to secure ASP.net web api?
web api became the key to programming web based interactions. it can be accessed by anyone and sometimes hackers use the api URl for wrong purposes and they steal the users data 
from the URL. so it is very important to secure the webapi by providing some security to the api. 
we can secure the API by adding authentication and autorization to the API so that only the allowed user can access the api.

Authentication -> it is a process that helps to identify and checck users by their creds such as password, username etc. to have access to the web api firstly it  is necessary 
 to pass the required details in the api's headers. if the user authenticated then only the user is allowed to call the api. if the user if unauthorized then will get 401 error.

Authorization -> its a process that helps to decide whether or not a user has access to perform an action. 


- What is CORS in web api?
CORS stands for Cross origin resource sharing. CORS solves the same-origin restriction for javascript. Same origin means js can only makes AJAX calls for web pages 
withing the same origin.  NOW with CORS we can enable to send the request through CORS. 

what new features comes with ASP.NET Web api 2.0?
- Attribute routing
- CORS
- HttpActionResult
- Web Api OData
- Open Web Interface NET
- External Authentication

- How can we restrict access to methods with specific HTTP verbs in Web api?
Attribute programming is widely used for this functionality. like [HttpPost]. Web api also allows restricting access of calling methods with the help of specific HTTP verbs.
it is also possible to define HTTP verbs as attribute over method.
 
 
HTTP Verbs -> HttpGet, HttpPut, HttpPost, HttpDelete, HttpPatch

Which protocol is supported by Web Api -> HTTP, therefore, it can be consumed by a client that supports HTTP protocol.

Difference between MVC and WEb Api -> MVC is used for developing applications that comes with user interfaces. the views in MVC are used to develop a user interface.web api is 
used for developing HTTP services.  to fetch data, the web api methods are called by other applications. 


Middleware Components -> Middleware components are the main building blocks of the asp.net core app request pipeline. they process the HTTP request in the app.

Interview Questions : 

What is ASP?
- Asp stands for Active server pages. and also known as classic ASP. it is a server-side technology provided by microsoft to create dynamic and user-friendly web pages.

What is ASP.NET?
- ASP.net is a specification by microsoft which is used to create web applications and web services. it is a part of .net framework. you can create web applications in all the 
languages which do support the .net.

What is IIS?
Internet INformation services. it is a service provided by microsoft to provide internet-base service to asp.net web applications.

What is the usage of IIS?

WHat is multilingual website?
- If a website provides content in many languages, it is known as a multilingual language. it contains multiple copies of its content in multiple languages.

What is Caching?
- Caching is the feature through which we can store the frequently used items in the memory so that they can be accessed quickly. and we don't need to go with server to get those
frequently used items again and again.

Main Requirements for Caching?
- By caching the response, we can reduce the api calls. 
- While caching we must need to be alert to only store the relevant details or which are not changing frequently because cache incurs overhead.
- A frequently used web form which data doesn't change frequently is good for cache.

What is  the concept of POSTBACK in ASP.net?
- Postback is a request which is sent from a client to server from the same page user is working with. There is an HTTP POST request mechanism in ASP.net. it posts a complete
page back to the server to refresh the whole page.

what is the use of isPostback property?
- the isPostback property of page object is used to check that  the page is posted back or not.

what is the difference between asp.net webforms and asp.net mVc?
asp.net webforms follows the page controller approach for rendering layout.in this approach, every page has its own controller. 
on the other hand, ASP.net mvc uses the Front Controller approach. in this  approach, there is a common controller for all the pages.

Difference between Sessionobject and Application object?
- SEssionObject is used to store the details of the user for that particular session. when the user enters into the application a userId is generated and 
the userId got destroyed when the user leaves the application and session got ends.

- ApplicationObject is used to store the information and access variable from any page in the application.

what is a cookie?
cookie is a small piece of data which gets stored at the  client side. it is of 2 typs:
-Session/Temporary Cookie -> stores only for a session
-Persistent Cookie -> valid for multiple sessions

Disadvantages of Cookies:
- Cookies can store only string value.
- Cookies are browser dependent.
- Cookies are not secure.
- Cookies can store only small amount of  data.

what is the file extension for web services -> .asmx 

what is the difference between namespace and assembly?
- an assembly is a physical grouping of logical units while namespace grouping classes.A namespace can span multiple assemblies.

Difference between hashTable and array list?
- Hash table stores data in the form of key value pair whereas array list stores only values.
- To access any value, need to pass key value in hashtable whereas in arraylist you need to pass the index number.

What is HTTPhandler?
HttpHandler is a low level request and response API which is made to service incoming HTTP requests. every request received by ASP.NEt is processed by an instance of a class
that implements HttpHandler.

what is manifest in .net framework?
- Manifest is used to store assembly metadata. it contains all the metadata which are necessary for the following things:
Version Of Assembly, Security Identity, Scope of the assembly

Which method is used to enforce Garbage Collection in .Net?
System.GC.Collect() method 

Difference between Dispose() and finalize()
- Although Dispose and Finalize both the functions are used by Garbage Collector during runtime to remove the unwanted objects but still there is some difference.
i.e The Finalize method is called automatically by the runtime whereas the dispose() method is called by the programmer.

What are tuples in .net?
- A tuple is a fixed size of collection  that can have elements of either same or different data type. the user must have to specify the size of the tuple
at the time of declaration just like array.

what is host in asp.net core?
- host encapsulates all the resources for the app. on startup, ASP.net core application creates the host. the resources which are encapsulated by the host includes:
HTTP Server Implementation, Dependency Injection, Configuration, Logging, Middleware Components.

Filters?
-Filters provide the capability to run the code before or  after the specified stage in the request processing  pipeline, it could be either MVC app or web api service.
filters performs the tasks like Authorization, Exception Handling , Cache Implementation etc. ASP.net core also provide the option to create custom filters. there 
are 5 types of filters supported in ASP.net core web apps or services. 
- Authorization filters run before all or first and determine whether the user is autorized or not.
- Resource filters are executed after the Authorization. OnResourceExecuting filter runs the code before rest of filter pipeline and onResourceExecuted runs the code
after rest of filter pipeline.
- Action Filters run the code before or after the action method execution. Action filters can change the arguments passed to the method and can change the result 
from the action method.
- Exception filters used to handle the exceptions globally before writing the response body.
- Result Filters allow to run the code just before or after the successful execution of action results.

why do we convert higher level language code into intermediate and then IL to machine level? why can't we directly compile the high level language to machine level 
like other languages?
- The reason is the different environments. during the development the environments may be different and during runtime environments may be different so depending
on the runtime environment JIT will compile the IL code to that specific runtime environment according to that environment which will suits better. so that's why.


Does .net support multiple languages?
yes

CLR -> 
Unmanaged COde -> unmanaged code have their own environment in which the code runs and its completely outside the control of CLR.

Common Type System (CTS) - AS .net framework can be supported in many programming language like C#, F#. so if any code is written in C# and we want to use that in 
F# then in every language we have their own syntax to deffine any variable like in C# int i = 0; and in F# Dim i as integer; so what the CLR does it converts all 
these types to a common type. CTS ensures that data types defined in two different language gets compiled to a common data type.

CLS -> Common Language Specifications -> CLS is a specification or set of rules. as we have different languages like C#, VB.net, F# and all of them are different. some
are case sensitive, some are not. so we do have a cls in which every language to follow that rule this way we can consume one language code into other language.

Generic Collection -> generic collection takes all the good things of array and arrayList. 

What are threads?
To achieve the parallel programming we need to use threads. Thread t = new Thread(Method 1); 

Why do we need the out keyword?
- IF we want to return multiple values from a function then we do use the out keyword. for eg: a function is returning sum but we want to return division, multiplication, 
and subtraction from the same function then we do use the out keyword.

What is dependency injection?
- DI is a methodology where rather than the caller creating the instance it's injected by some framework. like in StudentService if we want to use the IStudentservice
then we are not creating the instance of the IStudentService like IStudentService ins = new IStudentService(). 
but it's injected by the framework through the constructor.

Inversion Of Control -> Inversion of control is just a concept its not any software thing its just a concept any kind of unnecessary thing whatever you should 
delegate/assign it to someone else and that code should focus on his task not on other's task.

Benefit of Dependency  Injection -> u change at one place and the changes will reflect on multiple places. for eg. we are injecting dbContext in Studentservice and 
service does not know anything about what is this dbContext and now we wants to use OracleDB for dbContext file then we simply change in the StartUp file while 
adding the service in the ConfigureSErvices method and it will get changed and now again we want to change it to sqlserver and we just change that in startup file
and all the instances of that dbContext now point to sql server instance. so we are just changing in startup file but the changes are reflecting at all the places where
that dbContext is getting used.

SQL : Sql is a programming language designed for managing data in a relational database..sql has a variety of functions that enable its users to read, manipulate and change data.
 

Database and their Programming languages
RDBMS                SQL
MS SQL Server        T-SQL
Oracle               PL/SQL
MYSql                SQL




DBMS and RDBMS
- Dbms stores data as file whereas RDBMS stored data in tablular form.
- in Dbms no relation between data. but in RDBMS there is relation between data like foreign key.
- normalization is not present in DBMS wherease in RDBMS present.
- deal with small quantity of data whereas RDBMS deals with large data.

Constraint  in SQL -> Constraints are used to specify the rules for the data in  a table. if we put any constraint on any column then we defined a rule for the accepted data 
on that column.
like -> PrimaryKey Contraint, Foreign Key, not null, limit constraint, default constraint.

Difference between primary key and unique key?
- Primary key is a column that uniquely identifies each row in a table.  whereas unique key also contains the unique records but it does not necessarily serve as the primary identifier
for a row.
- can't have any null value in the primary key value whereas unique key can contain 1 null value in the table because null value is considered as a distinct value.
- there can be only 1 primary key in a table and primarly it is composed of only 1 column but sometimes can also be a composite key(collection of multiple columns.) whereas we can 
have multiple unique keys in a table.
- Creates Clustered index but unique key doesn't set clustered index.


Triggers : 
- Triggers are stored programs which are automatically occured when any specified event(insert, update, delete) occurs. if u want to track any update/delete event on a table 
then we do use triggers. 
Types of triggers. 
After Trigger and INstead of Triggers 

After Trigger -  in After trigger, we do define the condition in which after a certain event our trigger got executed. like on updation in a table an entry in the log table will 
be created.

Instead of trigger - its a trigger, whereas instead of doing the specified action it will perform the condition which is specified in the condition. 
for eg. Create Trigger [dbo].[Triigere2]
on [dbo].[students] INSTEAD OF  insert 
AS begin 
// logic here

end
 
 so in the above example when someone tries to insert any data in the students table then instead of inserting data it will perform the action specified in the logic mentioned in 
 the trigger.
 
 
 Difference between having and where clause?
- Having clause is used after group by clause and where clause is used before group by.
like -> select * from students where country = "india" GroupBy Country having Count(StudentId) > 5; 

- Having clause can contain aggregate functions whereas where clause can't contain aggregate functions.
eg. select name from students Group By name having SUM(StudentFees) < 3000 

Sub Query or Nested Query or Inner Query
Query inside the where clause of a query is known as Sub/Inner/Nested Query.


Auto Increment/Identity column in sql?
- Auto increment allows a unique number to be generated automatically when a new record is inserted into a table. 

what are joins in sql?
- Joins are used to combine rows from more than 1 table which have common columns in them.
for eg. select * from table1 JOIN table2 on table1.Id = table2.Id

Types of Joins- Inner JOIn, Left JoIN, right JOIn, Cross JOIN


Inner JOIn -> returns the common records from both the tables
Left JOIN -> returns all the  records of the left table and the common record from the right table
right JOIN ->  returns all the records of the right table and the common records from the left table
Cross JOIN -> Returns all the records from both tables
Self Join -> A self join is a regular join, but the table is joined with itself.
like select * from tableName where condition; simple query is the self join if there is no join mentioned in the query then there will be self join 

what is a cursor? why to avoid them

A cursor is a control which enables travelsal/iteration over the rows of a table.
its a 5 step process:

- Declare
- Open
- Fetch using while loop
- Close
- Deallocate

what is CTE in SQl server?
- Common table expression 


select * from table

select name, salary from table

rename column -> select name as StudetnName from table

LIMIT clause -> select * from table limit 2

Equal to = , != or <>, > , < , <=

arithmetic in SQL;

select name, age+ marks as StudentAgeMarks from table
select name, age*2 as StudentDoubleAge from table

Create table command -> Create table tableName(personid int, lastname varchar(255), firstName varchar(230));

Insert into command -> insert into tableName(personId, lastName, firstName) values(1,",")
if wants to insert values only for specific columnss then above query else if want to insert for all the fields then insert into tableName values();

TO check for the null check -> select * from tablename where age is null or age is not null 

Update statement -> update tableName set this= that, this1= that1, this2 = that2 where id=0;

delete statement -> delete from tablename where id=10;

Union Operator -> 

Difference between delete and truncate command?
- we can use where clause with the delete command. but not with the truncate command.
- we can delete the select records from the tablee with delete command but truncate will delete all the records from the table.
- delete locked the row during the transaction but truncate will lock the whole table.
- delete is a DML command whereas truncate is a DDL command.
- to use delete command u need the delete permission on the table and for truncate u need atleast alter permission on the table.
- we can add trigger on a delete condition in any table but can't add the trigger on the truncate command in any table.
- delete takes more transaction space than the truncate command because it delete the rows one by one whereas truncate takes less 
transaction space.

Difference between where and having clause?
- Where is used before the Group By command in any sql query whereas having used after the GroupBy command in the sql query.
- As where is used before groupBy so it applies on each and every row whereas having used after GroupBy command so it used only on the summarized records(got after group by).
- We can use aggregate functions(SUM, COUNT) with having but can't use with where clause that's why having came into the picture.
- Where can use with Update, Select, delete commands whereas having can only be used with selecct command.
- in the where clause the data is fetched from the table depending on the condition specified in the where clause whereas in having clause the whole data got fetched first 
and then condition appplied on the data.

DIfference between Primary key and unique key?
- PrimaryKey can't be null in any table whereas unique key can have 1 null value(because in some languages null treated as a distinct value).
- we can have only 1 primary key in table(with only 1 column or with multiple columns using composite key) but unique key can have multiple. 
- Primary key has a clusteered index by default whereas the unique key has non clustered index by default.
- Primary Key supports an auto increment value whereas a unique key doesn't support auto increment value.

Local Temporary table and Global Temporary table1
- a local temporary table is created by using a preffix of # whereas a global temporary table is created by using a prefix of ##.
- a local termp table can't be shared among multiple users whereas a global temp table can be shared among multiple users.
- a local temp table is available only to the current db connection for the current user and got cleared once the connection is close whereas a global temporary table  is 
available to any connection once created. they are cleared when the last connection is closed.

what is  database normalization?
database normalization is a process of analyzing the given relation schemas based on their functional dependecies and primary keys to achieve the following properties:
- Minimizing Redundancy
- Minimizing the update, delete and insertion anomalies 

Relations schemas that do not meet the properties are decomposed into smaller relation schemas that could meet the prooperties.

What are the  differences between DDL, DML, DCL?
DDL -> Data Definition Langugage, DML -> Data Manipulation Language, DCL -> Data Control Language

DDL -> DDL is used to define the structure that holds the data. SQL queries like -> create, drop, alter, rename ARCD   ARCD -> alter, rename, create, drop
DML -> DML is used for manipulation of the data. Update, Select and Insert -> IUS       -> IUS -> insert, update, select 
DCL -> DCL is used to control the visibility of data like granting database access and set priviliges to create the table, delete the table. Grant and Revoke -> grant and revoke 

What is identity ->   
identity is a column which automatically generates numeric values. in most of the scenarios its default value is 1. but we can also set its default value.

What is a view?
- a view is a virtual table based on a result set of a SQL statement. we can create view using the below syntax:

Create VIEW viewName AS select * from tableName where condition;

Advantages of View -> 
- View provide access restrictions, since data insertion, updation and deletion is not possible on the view.
- View don't store data in a physical location.
- View can be use to hide some of the columns from a table. 

Disadvantages:-
-When a table is deleted, the associated vieww to that table beccomes irrelevant.
- When views are created for a large table, it occupy large space in memory. 

Stored Procedure -> Stored Procedures is like a function that contains a set of operations compiled together. it contains a set of operations that are commonly used in an application 
to do the database related tasks. 

Difference between trigger and Stored Procedure?
Unlike Stored Procedures triggers can't called directly they would be associated to any action in a table and will get called automatically.  
 
what is database lock?
- database lock tells a transaction, if the data item in questions is currently being used by any other transaction. 
Type of locks:
- Shared Lock, Exclusive Lock

Shared Lock -> when a shared lock is applied on a data item, other transactions can only read the data item, but can't write into it.

Exclusive Lock -> When a exclusive lock is applied on data item, other transactions can't read or write into the data item.

why do we need locking in sql server -> we need locking in the multi user environment. suppose if user1 is updating a row in the table and at the same time user2 try to selecting 
that row than the database anomaly will occur. to handle this data concurrency we do use locking. '


What is a composite key?
- a composite key is a type of candidate key, which represents a set of columns whose values uniquely identify every row in a table. 

for  eg: if studetnId and StudentName in a table is combined to uniquely identifies a row is called a composite key. it formed by a collection of more that 1 key which can 
uniqely identify the row. in this case, both the case are represented as a primary key.

What is a transaction & what are ACID properties?
- Transaction is a set of database operations that must be treated as whole, means either all operations of the transactions are executed or none of them. 
Database transaction take database from one state to another. at the end of the transaction the system must be in the prior state if transaction fails or the status of the system 
should reflect the successful transaction. Properties of transaction are ACID. 
for eg. A bank transaction from one account to another account. either both debit and credit operations must be executed or none of them. 
ACID -> (Atomicity, Consistency, Isolation and Durability) is a set of properties that guarantee that database transactions are processed reliably.

Atomicity -> a transaction consist of many steps. when all the steps in a transaction gets completed, it will get reflected in the DB or if any step fails, all the transaction 
are rolled back.

Consistency -> the database will move from one database state to another if the transaction executed successfully and remain in the original state if the transaction fails.

Isolation -> Every transaction should operate as if it is the only transaction in the system.

Durability -> Once a transaction has completed successfully, the updated rows/records must be available for other transactions on a permanent basis.

what is a field in a database?
- A field is an area within a record reserved for a specific piece of data.
eg. Employee Name, Employee Salary etc. 

What is a record in database?
- A record is the collection of values/fields of a speacific entity. 

What are wild cards used in database for  pattern matching?
- SQL LIKE operator is used for pattern matching. SQL 'LIKE' commands takes more time to process. so always try to avoid the like operator and try to use any other operator 
if possible. we should never put the like operator in the starting of the query always try to put the like operator in the end of the query so that less records got filtered. 
POINTS to remember:
1. Don't overuse wild cards.if another search operator can do its work then use that operator instead of like.
2. When you use wild cards, try not to use them at the beginning of the search pattern, unless absolutely necessary.
3. Pay careful attention to the placement of the wild cards symbol. if they are misplaces, you  might not return the data you intended.


JOINs and different types of JOINS?
- In order to avoid date dupliation, data is stored in the related tables. JOIN keyword is used to fetch data from related tables. JOIN return rows when there is at least one match 
in both the tables. 

- Right JOIN -> Return all rows from right table, even if there is no match in the left table. and the common from left table.
- left JOIN -> Return all rows from left table, even if there are no matchess in the rigth table.
- Full JOIN -> Return rows when there is a match in one of the tables. 


Difference between Truncate, Delete and Drop commands?
- Once delete operation is performed, commit and rollback can be performed to retrieve the data.
- Once truncate statement is executed, commit and rollback statement can't be performed.
- Drop command is used to drop the table or keys like primary, foreign from a table.

How do you create a unique constraint on a table?
- we can define unique constraint while Creating table or we can explicitly add the unique constraint on the table. Unique constraint can be applied to one or more columns means those
columns can't have duplicate values in the table. 

for eg. 

alter table tableName Add Constraint constraintName UNIQUE(column name);

for eg: if we want to add constraint on the email column in the student table then 

alter table student Add Constraint unique_email UNIQUE(emailAddress);   -> also write multiple columns in a single go 

while defining the table:

create table student( id int Primary Key, userName varchar(20), email varchar(15) UNIQUE)

## What is the purpose of an index in SQL, and how do you create one?
- An index in sql is a database object that is used to improve the speed of data retrieval operations on a table. it acts like a data structure that stores a subset of the data 
from the table and organizes it in a way that makes it faster to search for specific rows based on the indexed columns. the main purpose of it is 
1. Improving Query Performance
2. Enforcing Uniqueness

create index index_name on table_name(Column_name);

##What is normalization, and why is it important in database design?
Normalization is a crucial concept in the field of database design. it is the process of organizing data in such a way that data redundancy is minimized, data integrity is ensured, 
and data consistency is maintained.
CIR process -> consistency, integrity and redundancy

the main goal of normalization is to remove the data anomalies such as updat anomalies, delet and insert anomalies , which can occur when the data is stored in a denormalized 
or unstructured way. 

Normalization is important for the following reasons.
Data Integrity, Improved Query Performance, 

Normalization can be achieved through the series of normal forms, each building upon the previous one. the most common are:

1NF -> First Normal Form -> It ensures that each column in a table contains atomic(indivisible) values, and there are no repeating groups.
2NF -> Second Normal Form -> in addition to 1NF, 2NF ensures that non-key attributes are functionallly dependent on the entire primary key, not just part of it. 
3NF -> in addition to 2NF -> 3NF eliminates transitive dependencies between non key attributes.


##Explain the concept of a self-join in SQL.
- A self join in sql is a join where a table is joined with itself. this is typically done when a table contains hierarchical or recursive data or when u want to compare the rows
within the same table. 

##What is an aggregate function in SQL, and give examples.
An aggregate function is a function that performs a calculation on a set of values and returns a single, summarized result. Aggregate functions are performed on groups of 
rows defined by the 'GROUP BY' clause. 

eg. COUNT, SUM, AVG, MIN, MAX, GROUP_CONCAT, VAR, COUNT(DISTINCT)

##What is a subquery, and how is it different from a JOIN?
A subquery(inner query or nested query) is a sql query embedded within other sql query. subqueries are used to retrieve data from one or more tables and then use that result as part
of the main query. 

eg. select * from employees where salary > (select AVG(salary) from employees);

A join on the other hand is used to combine  2 or more tables based on a related column between them. it is used to retrieve data from multiple tables by specifying how  the tables
are associated. 

##What are common SQL optimization techniques?
Sql optimization is the process of improving the performance of sql and database operations to reduce query execution time and resource consumption. here are the some common sql 
optimization techniques:
- indexing - use proper indexing for the columns used in where conditions can increase the performance and reduce the query time. 
- Avoid Select - try to avoid selecting all the columns of a table instead select only the required columns. 
- use limit or top - instead of selecting all the records fetch top 100 records or how much u want.
- Avoid Subqueries when possible
- avoid Using Wildcards at the beginning of like patterns: 
- USE union all- when selecting data from multiple tables combined then instead of using union all instead of union. this will remove the extra checking  of duplicate rows.
- Avoid using Distinct unnecessarily
- Use exists and not exists
- Avoid cursors
- Caching - use caching to store frequently accessed data


##Explain the difference between UNION and UNION ALL.
When to use UNION or UNION ALL depends on your specific needs:
- Use UNION when you want to combine result sets and ensure that there are no duplicate rows in the final output. This is useful when you want a merged list
 of unique values from multiple queries.
- Use UNION ALL when you want to combine result sets and retain all rows, including duplicates. This can be beneficial when you don't need to eliminate duplicates or when
 you want to optimize query performance by avoiding the extra processing required to remove duplicates.

In summary, UNION removes duplicate rows from the final result set, while UNION ALL includes all rows, including duplicates, in the final output. Your choice between the
 two operators depends on the specific data requirements of your query.
 
##Explain the difference between a clustered and non-clustered index.
- Clustered and non-clustered indexes are 2 main parts of the indexing in database system to improve the speed of data retrieval. they differ in their structure, organization, 
and the way they store and retrieve data.

Clustered Index:
- Physical order - the  rows of the table are stored on the disk in the same order as the clusteered index.
- One Per table - a table can have only 1 clustered index. this index organizes the whole table.
- Performance Impact - when u perform a query that involves the column covered by the clustered index, it will quickly retrieve data since it follows the physical order.
- Key Columns - The columns included in the clustered index are called the clustered key. 

ex. Create Clustered clusteredName on Employee(EmployeeName);

Non Clustered Index:
- Logical Order- A non clustered index does not dictate the physical order of rows. Instead, it creates a seperate data structure that contains pointers to actual rows. 
- Multiple Per table- a table can have multiple non-clustered index.
- Performance Impact- they are not as fast as clustered indexes because they have to look additional lookups for  actual data.
- Key Columns- the columns included in teh non clusteered  index are known as non-clustered keys. 
\

##What is the purpose of the TRUNCATE statement?
- Truncate statement deletes all the rows of a table in a single go but it does not change the schema of the table. 

Truncate table tableName;  

##How do you create and use temporary tables in SQL?
- Temporary tables in sql are very helpful to store the data specific to a session. they are temporary in nature and got clean after the session got end. 

Create Table #tempTable(id int, name varchar(50))

once u created a temp table u can use it like any other table. 
like insert into #tempTable values(1,"Dhruv");

dropping a temporary table -> drop table #tempTable;

its important to note taht the naming convention and the behaviour of the temporary tables may vary different database systems. in some systems, temp tables are local to a session 
and removed automatically when the sesssion ends but in some database system they are global we need to remove them explicitly. so according to the database systems it depends.

##Explain the purpose of the SQL CASE statement.
- the sql CASE statement is used to conditionally execute sql statements, returning different values or performing different actions based on the difffernet conditions.it provides 
a way to create conditional logic withing sql queries. 

case 
when condition1 then execute 1
when condition2 then execute 2

else result

END

we need to add the END keyword for every case statment in the end. 



Ques -> find the second highest salary from a table 

select max(salary) from employee where salary not in(select max(salary) from employee);

que -> sleect the max salary of the emloyee department wise

select max(salary), department from demo group by department
 
que -> select the no. of employees department wise

select count(*), department from demo group by department

que -> display alternate records in sql either even no. or odd no. 

we have a rownum column and this column is readonly. we can't write on it. and we can't use * with this so need to define the column no. 

quer -> display alternate records
	
	
que -> select the duplicate records 

select name, count() from demo group by name having count() > 1

que -> display the employees name having  m in any position in their name
select employeeName from demo where name like '%M%'	

ue -> display the employees name does not contain  m in any position in their name
select employeeName from demo where name not like %M%'

que -> display name whose name contains exactly 4 letters
select name from demo where name like '__'  <- 4 underscores

que -> whose name contain 2 letter as L and 4th letter as M%
sele3ct name from demo where name like 'L%'  and select name from demo where name like '___M%'

que -> select the employee name and hire dates for the employee joined in the month of decemebt
select empName, hireDates from demo where joinedDate like '%DEC%'   <- coz the joined date will contain decc

que -> name which contains exactly 2Ls -> 
select name from demo where name like '%LL%'

que -> whose name starts with J and ends with S  -> select * from demo where name 'J%S'

que ->display nth row in sql like display 2nd or 4th row of the table

que -> union all and union -> if we are using union on 2 tables and 2 tables have the same row in both tables then in result will get only 1 but in union all will get both 2 records.

que -> how to find the nth largest salary  

select top 1 (select distinct top 3 salary from demo order by salary desc) result order by  salary   -> if wants to find 5th largest salary then change 3 to 5

Destructors are also known as Finalizers.

what is oauth stands for   -> oauth stands for open authorization. and it's an open standard and protocol that allows secure access to a user's data on one website. 

what is JWT -> 	jWT stands for JSON web tokens. it is basically used for authentication and authorization purposes in web applications and api's.they are particularly popular
in single sign on(SSO) systems and securely transmitting claims between parties. 

A JWT is composed of 3 parts:
- Header -> header typically consist of 2 parts -> type of token(jwt), signing algorithm being used(SHA256 or RSA). it is encoded in base64 url.
- Payload -> payload contains claims. claims are statements about an entity(typically the user) and additional data. payload is also encoded in base64 url.
- Signature -> signature of the token is used to verify that the sender of the JWT is who it says it is and to ensure that the message was not changed along the way.


the result of these 3 result into a jwt token that is being shared between the parties. 


difference between IActionResult and HttpResponse -> IActionResult and HttpResponse both related to handling HTTP responses in asp.net core, but they serve different 
purpose. 

IActionResult -> IActionResult is an interface in asp.net core which is used to define the result of an action method in a controller.
-  It represents the result of an action and allows you to return various type of result such as views, JSON data, redirections and more.
- by using IActionResult we can implement controller actions that are more abstract and return different type of results depending on the situation. 
- IActionResult is a higher level, abstract concept that does not deal with the low level HTTP response details. 

HttpResponse -> Http response is a lower level concept that represents the actual HTTP response being sent to the client.
- It allows you to deal with HTTP response headers, status codes and response content directly. 
- it is used when u need to perform low level response handling. 



302 status code  -> Temporary Redirect

what is rest and restful   -> REST as we know and REstful -> Restful is just an adjust used to represent the service which got created by following the REST principles.
A service or application is called Restful if it follows REST constraints, such as using HTTP methods as intended, having a clear seperation between client and server and being
stateless.


what are the type of authentication in mvc  -> MVC provides u the various authentication mechanisms to secure your web applications. some common types are:
1. Window Authentication -> uses windows authentication for the login and other tasks
2. Form Authentication -> like on form by entering the userName and passwords
3. ASP.net Identity -> ASP.net identity is a membership system introduced in asp.net, designed to handle authentication, authorization.
4. OAuth and OpenId Connect -> 
5. Bearer Token Authentication -> on successfull login a token gets generatd which is passed to backend api's.
6. API key authentication -> where u need to secure the api's.

the choice depends on u which type of security requirements u have in yourr application.

	
difference between iis and kestrel server -> Internet Information Services and Kestrel
- IIS is a full-fledged web server  that has been widely used for hosting various type  of web applications, including asp.net applications. kestrel, is a lightweight purpose 
built weeb server specifically designed for Asp.net core applications.

- IIS is a window specific and can be used only for hosting applications on windows servers. Kestrel is cross platform and can run on windows, linux and macOS.
- in Production environments, kestrel and IIS are both used together to serve web applications efficientlly and securely. the IIS is used for tasks like SSL termination, load 
balancing and security while kestrel used for serving the asp.net core application itself. 


how can we transfer data from controller to view  -> we can transfer data from controller to view by following methods:
1.ViewData -> we can use the viewData dictionary to pass small amount of data from controller to view . ViewData is a key-value dictionary provided by the controller for this
purpose.

public IActionResult MyAction(){
ViewData["Message"] = "Hi GoodAfterNoon";
return View(); 
}

in view: 

<div>@ViewData["Message"]</div>


2. ViewBag -> similar to viewData u can use the ViewBag dynamic  property to send the data from controller to view. it provides a more dynamic way of accessing data in a view.

controller : 

public IActionResult MyAction(){
ViewBag.Message = "Hi GoodAfterNoon!";
return View();
}

in view:

<div>@ViewBag.Message</div>

3. Model -> this is the most safest way of sending data from controller to view. its a strongly typed method. you define a model calss in controller, populate the data and pass it 
to view.

public class MyModel{
public string Message{get;set;}

}
public IActionResult MyAction(){
MyModel myModel = new MyModel();
myMode.Message = "Hi GoodAfterNoon!";
return View(myModel);
}


in View :
@model MyModel 
<div>@model.Message</div>

4. TempData -> Tempdata is used to store data for the duration of an HTTP request and is often used for scenarios where u need to pass data from 1 action method to another. it 
can also be used to pass data to the next request after a redirect. 


Controller:

public IActionResult MyAction(){
TempDatea["Message"] = "Hi GoodAfterNoon";
return RedirectToAction("AnotherAction")
}

AnotherAction:

public IActionResult AnotherAction(){
string message = TempData["Message"];
return View();
}

View for Another Action:

<div>@message</div>

the most recommended approach is to use a strongly typed model for passing data to the view wheneve possible as it provides compile-time checking and better code organization.

how can pass model to the view  -> 
in asp.net mvc we can pass a model to the view by setting the model of the view to the desired type using the @model directive at the top of the view.this is known as strongly 
typed view. 


first need to create a model
public class MyModel{
public string Message{get;set;}
}

then create a controller - 
public IActionResult MyAction(){
MyModel myModel = new MyModel();
myMode.Message = "Hi GoodAfterNoon!";
return View(myModel);
}


in View :
@model MyModel 

<div>@model.Message</div>

with this the data we populated in the controller action method in the model will be available in the view. 



what is jquery and ajax   -> 
validations in mvc  -> 
how can we handle the exceptions in mvc   -> By creating custom error pages, by Global Exception Handling, Controller level exception handling, View-Level Exception handling,
Logging, Custom Error pages


example of abstraction and encapsualation
abstraction -> it  allows u to focus on what an object does rather than how it does it. for eg. compilation process.

encapsualation -> encapsualation is to hiding the internal details and state of an object. for eg. class.
[3:48 pm, 18/11/2023] dHrUv SiR(iNnOsTaX): What are the RestFul services?
- Rest stands for Representational State Transfer. REST is an architectural pattern used for exchanging data over a distributed network. REST architectural pattern treat every
service as a resource and client can access these resources by using HTTP protocol methods such as GEt, post, put, delete and patch. the REST architectural pattern specifies a 
set of constraints such as:

1. Client-Server Constraint -> this is the first constraint. in this client sends a request to the server and server processes the request and then returns the result back to the 
client. this seperation of concerns supports the independent development of client and server. in this client and server both are independent of each other. client just need 
to know the url and sends the request to the server. 

2. Stateless Constraint -> thee next constraint is the Stateless constraint. in this client and server both are stateless to the request. server does not store any information 
regarding the client. the request from the client should contain all the necessary information so that server can identify that who the client is.

3. Cacheable constraint -> this is the 3rd constraint. and in this server has some data which don't change frequently like name of countries. the constraint is that let the 
client know about this data so that client don't request for the data and can store the data in cache memory.

4. Uniform Interface Constraint -> Uniform interface constraint is an interface between the client and server. to know the uniform interface constraint, we first need to know
about resource and the httpmethods. resource is basically a data entity like country, State, Customer etc and the http methods like put, patch, delete, get, post are used to 
tell what we need to do with these resource. Each resource is identified by a specific URI.

5. Content Negotiation -> Content negotiation is also a constraint which states that the client should have the ability to decide in which format it needs the response - like in 
JSON or XML. this is called content negotiation. we can define content negotiation as the process of selecting the best representation for a given response when multiple 
representation are present.

6. Layered System -> Rest allow us a layered system architecture. in this we deploy the APi on server A, store data on Server B, and authenticate the api's on server C. for example, 
a client cannot ordinarily tell whether it is connected directly to the server or to intermediary along the way.



Difference between SOAP and REST?

  REST                                                                            SOAP
1. Representational State Transfer.                                           Simple Object Access Protocol
Its an Architectual pattern.                                                   its an XML based protocol.
Its completely stateless.                                                     its stateful as well as stateless.
it does not enforce message format as XML                                      it forces message format as XML.
or JSON. 
Performance is fast.                                                          slow performance. 
it uses the HTTP built in headers to store the information and uses     soap message consist of an envelope that includes soap headers and a body to store the actual 
the http methods such as get, put, post to perform CRUD operation.          information we want to send. 


# Content Negotiation -> content negotiation is the process where the client should have the ability to decide in which format they wants the response from the server. whther in 
XML or in JSON. This is called content negotiation. and we can also define it as : the process of selecting the best representation when there are multiple representation present.

Content Negotiation means client and server can negotiate that's why its negotiation not demand. in such cases the server will return the data in the requested format.

now the question is how does the server know in which format client wants the data ? -> that is defined in the headers of the request.

1. Content-type -> the content-type header value requests the server to represent data in this format. the values can be application/xml and application/json.
2. Accept -> The accept header value represents the media types that are acceptable for the response. such as application/json and application/xml.
3. Accept-charset -> utf-8
4. Accept-encoding
5. Accept-Language


# What does the Web Api Framework do when we request data in a specific format?
- the controller action method first get the response which needs to send to the client. suppose client wants the list of students then first it will fetch the list of students
and then hands the data to the web api pipeline which then looks at the accept header value, and depending on the format that the client has requested, the web api framework 
will choose the appropriate formatter.

# Parameter Binding in Web Api -> the parameter binding means how the web api framework binds the requesting parameter with the action method parameter. generally we takes the 
value which are liek primitive data type in the query string and then those value get mapped to the parameter of the endpoint . if the request is complex then the web api 
tries to get the request from the body. as in get and ddelete request we can't take the data from the body.
[3:48 pm, 18/11/2023] dHrUv SiR(iNnOsTaX): LINQ -> Language Integrated Query  and it is a set of features introduced in c# and vb.net that allows u to query and manipulate the data acccordingly.


ICS -> initialization, Condition, Selection 

we have 2 ways to write LINQ 
1. Query Syntax
2. Method syntax
3. Mixed syntax

Linq query syntax -> ICS approach like   from item in items where value> 5 select item;

Linq method syntax -> var QuerySyntax = integerList.Where(obj => obj > 5).ToList(); 


Linq supports chaining syntax 
var result = collection
             .Where(item => item.SomeProperty > 10)
             .OrderBy(item => item.SomeProperty)
             .Select(item => item.SomeValue);
			 
Advantages of LINQ -> 
1. Simplicity and Readability:
2.Type Safety:
3.Code Reusability:
4.Efficient Execution:

Disadvantages of LINQ ->
1. Performance Overhead:
2. Learning Curve
3. Database Queries:
4. Debugging Complexity


lambda Operator -> The lambda operator, often represented as the "=>" symbol, is a feature in many modern programming languages, including C#, that allows you to create 
anonymous functions or delegates in a more concise and expressive way.Lambda expressions are a powerful feature in C# that simplifies the creation of small, inline functions. 
They are often used in scenarios where you need to pass a function as an argument to another method (e.g., LINQ methods like Where, Select, etc.), define event handlers, or
 create delegates with minimal code overhead. Lambda expressions can make code more concise and expressive, especially when working with collections and functional programming 
 constructs.



(parameters) => expression 

parameters are the input parameters or arguments to the lambda expression.
=> is the lambda operator.
expression is the code or operation to be performed using the input parameters.


how to join two tables in linq and store response in 1 model 


suppose we have the following data:

 List<Customer> customers = new List<Customer>
        {
            new Customer { CustomerID = 1, CustomerName = "Customer A" },
            new Customer { CustomerID = 2, CustomerName = "Customer B" },
        };

        List<Order> orders = new List<Order>
        {
            new Order { OrderID = 101, CustomerID = 1, ProductName = "Product X" },
            new Order { OrderID = 102, CustomerID = 2, ProductName = "Product Y" },
        };

	from customer in customers join order in order on customer.CustomerID equals order.CustomerId select new {customer.customerId, order.OrderId, order.ProductName};
[3:48 pm, 18/11/2023] dHrUv SiR(iNnOsTaX): What is the use of ViewModel in MVC? -> ViewModel is a plain class with properties, which is used to bind it to strongly typed view. ViewModel can have the validation rules
defined for its properties using data annotation. 

13) How to enable Attribute Routing?

Just add the method – “MapMvcAttributeRoutes()” to enable attribute routing as shown below

public static void RegisterRoutes(RouteCollection routes)

{

routes.IgnoareRoute("{resource}.axd/{*pathInfo}");

//enabling attribute routing

routes.MapMvcAttributeRoutes();

//convention-based routing

routes.MapRoute

(

name: "Default",

url: "{controller}/{action}/{id}",

defaults: new { controller = "Customer", action = "GetCustomerList", id = UrlParameter.Optional }

);

}

Need to check how do we enable attribute and convention routing in mvc and asp.net core?

for convention based routing need to define the below line in the COnfigure method in startup file 

app.UseEndpoints(endpoints =>
{
    endpoints.MapControllerRoute(
        name: "default",
        pattern: "{controller=Home}/{action=Index}/{id?}");
});



- JQUERY,AJAx need to learn in mvc

- Explain JSON Binding?

JavaScript Object Notation (JSON) binding support started from MVC3 onwards via the new JsonValueProviderFactory, which allows the action methods to accept 
and model-bind data in JSON format. This is useful in Ajax scenarios like client templates and data binding that need to post data back to the server

How route table has been created in ASP.NET MVC?

Method – “RegisterRoutes()” is used for registering the routes which will be added in “Application_Start()” method of global.asax file, which is fired when 
the application is loaded or started.

- NEED to check the differencce between viewdata and  viewbag 

- Explain TempData in MVC?

TempData is again a key, value pair as ViewData. This is derived from “TempDataDictionary” class. TempData is used when the data is to be used in two consecutive requests, 
this could be between the actions or between the controllers. This requires typecasting in view.

Can you explain RenderBody and RenderPage in MVC?

RenderBody is like ContentPlaceHolder in web forms. This will exist in layout page and it will render the child pages/views. Layout page will have only one RenderBody() method. 
RenderPage also exists in Layout page and multiple RenderPage() can be there in Layout page.

 What is ViewStart Page in MVC?

This page is used to make sure common layout page will be used for multiple views. Code written in this file will be executed first when application is being loaded.

29) Explain the methods used to render the views in MVC?

Below are the methods used to render the views from action -

View() – To return the view from action.

PartialView() – To return the partial view from action.

RedirectToAction() – To Redirect to different action which can be in same controller or in different controller.

Redirect() – Similar to “Response.Redirect()” in webforms, used to redirect to specified URL.

RedirectToRoute() – Redirect to action from the specified URL but URL in the route table has been matched.

What is the "HelperPage.IsAjax" Property?

The HelperPage.IsAjax property gets a value that indicates whether Ajax is being used during the request of the Web page.

Why to use Html.Partial in MVC?

This method is used to render the specified partial view as an HTML string. This method does not depend on any action methods. We can use this like below –

@Html.Partial("TestPartialView")

What is Html.RenderPartial?

Result of the method – “RenderPartial” is directly written to the HTML response. This method does not return anything (void). This method also does not depend on action methods. 
RenderPartial() method calls “Write()” internally and we have to make sure that “RenderPartial” method is enclosed in the bracket. Below is the sample code snippet
 –@{Html.RenderPartial("TestPartialView"); }
 
 What is RouteConfig.cs in MVC 4?

"RouteConfig.cs" holds the routing configuration for MVC. RouteConfig will be initialized on Application_Start event registered in Global.asax.


What are Scaffold templates in MVC?

Scaffolding in ASP.NET MVC is used to generate the Controllers,Model and Views for create, read, update, and delete (CRUD) functionality in an application.
 The scaffolding will be knowing the naming conventions used for models and controllers and views.
 
 Can a view be shared across multiple controllers? If Yes, How we can do that?

Yes, we can share a view across multiple controllers. We can put the view in the “Shared” folder. When we create a new MVC Project we can see the Layout page will be added in
 the shared folder, which is because it is used by multiple child pages.
 
What are the possible Razor view extensions?

Below are the two types of extensions razor view can have –

.cshtml – In C# programming language this extension will be used.

.vbhtml - In VB programming language this extension will be used.


What is PartialView in MVC?

PartialView is similar to UserControls in traditional web forms. For re-usability purpose partial views are used. Since it’s been shared with multiple views these are kept in
 shared folder. Partial Views can be rendered in following ways –

Html.Partial()

Html.RenderPartial()

What is the difference between public, static, and void?

Public declared variables or methods are accessible anywhere in the application. Static declared variables or methods are globally accessible without creating an instance 
of the class. Static member are by default not globally accessible it depends upon the type of access modified used. The compiler stores the address of the method as the 
entry point and uses this information to begin execution before any objects are created. And Void is a type modifier that states that the method or variable does not return 
any value. 

What is the use of ‘using’ statement in C#?

The ‘using’ block is used to obtain a resource and process it and then automatically dispose of when the execution of the block completed.


Can we use “this” command within a static method?

We can’t use ‘This’ in a static method because we can only use static variables/methods in a static method.


How can we sort the elements of the Array in descending order?

Using Sort() methods followed by Reverse() method.


What are circular references?

Circular reference is situation in which two or more resources are interdependent on each other causes the lock condition and make the resources unusable.


What is an object pool in .NET?

An object pool is a container having objects ready to be used. It tracks the object that is currently in use, total number of objects in the pool. This reduces the overhead of 
creating and re-creating objects.


What is the difference between a Struct and a Class?

Structs are value-type variables, and classes are reference types. Structs stored on the Stack causes additional overhead but faster retrieval. Structs cannot be inherited.

What is difference between the “throw” and “throw ex” in .NET?

“Throw” statement preserves original error stack whereas “throw ex” have the stack trace from their throw point. It is always advised to use “throw” because it provides more
 accurate error information.


What is meant by an Interface?
An interface is a class that does not have any implementation. Only the declarations of events,

What is the Race condition in C#?
When 2 threads access the same resource and try to change it at the same time, we have a race condition. 

What is Thread Pooling in C#?
In C#, a Thread Pool is a group of threads. These threads are used to do work without interfering with the principal thread’s operation.


What is an Escape Sequence? Name some String escape sequences in C#.

Answer: An Escape sequence is denoted by a backslash (\). The backslash indicates that the character that follows it should be interpreted literally or it is a special character. An 
escapen sequence is considered as a single character.

String escape sequences are as follows:

\n – Newline character
\b – Backspace
\\ – Backslash
\’ – Single quote
\’’ – Double Quote


 What is a Thread? What is Multithreading?

Answer: A Thread is a set of instructions that can be executed, which will enable our program to perform concurrent processing. Concurrent processing helps us do more than one
 operation at a time. By default, C# has only one thread. But the other threads can be created to execute the code in parallel with the original thread.

Thread has a life cycle. It starts whenever a thread class is created and is terminated after the execution. System.Threading is the namespace which needs to be included to create
 threads and use its members.

Threads are created by extending the Thread Class. Start() method is used to begin thread execution.

C# can execute more than one task at a time. This is done by handling different processes by different threads. This is called MultiThreading.

There are several thread methods that are used to handle multi-threaded operations:

Start, Sleep, Abort, Suspend, Resume and Join.

Most of these methods are self-explanatory.

 Name some properties of Thread Class.

Answer: Few Properties of thread class are:

IsAlive – contains value True when a thread is Active.
Name – Can return the name of the thread. Also, can set a name for the thread.
Priority – returns the prioritized value of the task set by the operating system.
IsBackground – gets or sets a value which indicates whether a thread should be a background process or foreground.
ThreadState– describes the thread state.

What are the different states of a Thread?

Answer: Different states of a thread are:

Unstarted – Thread is created.

Running – Thread starts execution.
WaitSleepJoin – Thread calls sleep, calls wait on another object and calls join on another thread.
Suspended – Thread has been suspended.
Aborted – Thread is dead but not changed to state stopped.
Stopped – Thread has stopped.

What is a Deadlock?

Answer: A Deadlock is a situation where a process is not able to complete its execution because two or more processes are waiting for each other to finish. This usually occurs in
 multi-threading.

Here a shared resource is being held by a process and another process is waiting for the first process to release it and the thread holding the locked item is waiting for another
 process to complete.
 
 Explain Lock, Monitors, and Mutex Object in Threading.

Answer: Lock keyword ensures that only one thread can enter a particular section of the code at any given time. In the above Example, lock(ObjA) means the lock is placed 
on ObjA until this process releases it, no other thread can access ObjA.

Mutex is also like a lock but it can work across multiple processes at a time. WaitOne() is used to lock and ReleaseMutex() is used to release the lock. But Mutex is slower
 than lock as it takes time to acquire and release it.

Monitor.Enter and Monitor.Exit implements lock internally. a lock is a shortcut for Monitors. lock(objA) internally calls.


What is a Race Condition?

Ans: Race condition occurs when two threads access the same resource and are trying to change it at the same time. The thread which will be able to access the resource first 
cannot be predicted.

If we have two threads, T1 and T2, and they are trying to access a shared resource called X. And if both the threads try to write a value to X, the last value written to X 
will be saved.

What is Thread Pooling?

Ans: Thread pool is a collection of threads. These threads can be used to perform tasks without disturbing the primary thread. Once the thread completes the task, the thread returns to the pool.

System.Threading.ThreadPool namespace has classes that manage the threads in the pool and+
its operations.

System.Threading.ThreadPool.QueueUserWorkItem(new System.Threading.WaitCallback(SomeTask));
The above line queues a task. SomeTask methods should have a parameter of type Object.



What is Serialization?

Answer: Serialization is a process of converting code to its binary format. Once it is converted to bytes, it can be easily stored and written to a disk or any such storage devices. 
Serializations are mainly useful when we do not want to lose the original form of the code and it can be retrieved anytime in the future.

Any class which is marked with the attribute [Serializable] will be converted to its binary form.

The reverse process of getting the C# code back from the binary form is called Deserialization.

To Serialize an object we need the object to be serialized, a stream that can contain the serialized object and namespace System.Runtime.Serialization can contain classes 
for serialization.

What are the types of Serialization?

Answer: The different types of Serialization are: 

XML serialization – It serializes all the public properties to the XML document. Since the data is in XML format, it can be easily read and manipulated in various formats.
 The classes reside in System.sml.Serialization. 
SOAP – Classes reside in System.Runtime.Serialization. Similar to XML but produces a complete SOAP compliant envelope that can be used by any system that understands SOAP.
Binary Serialization – Allows any code to be converted to its binary form. Can serialize and restore public and non-public properties. It is faster and occupies less space.


What is an XSD file?

Answer: An XSD file stands for XML Schema Definition. It gives a structure for the XML file. It means it decides the elements that the XML should have and in what order and
 what properties should be present. Without an XSD file associated with XML, the XML can have any tags, any attributes, and any elements.

Xsd.exe tool converts the files to the XSD format. During Serialization of C# code, the classes are converted to XSD compliant format by xsd.exe.

What are dynamic type variables in C#?
Answer

You can store any type of value in the dynamic data type variable. Type checking for these types of variables takes place at run-time.

What is lambda expressions in C#?
Answer

A lambda expression is an anonymous function that you can use to create delegates or expression tree types. By using lambda expressions, you can write local functions that can
 be passed as arguments or returned as the value of function calls. Lambda expressions are particularly helpful for writing LINQ query expressions.

In the following example, the lambda expression x => x * x, which specifies a parameter that’s named x and returns the value of x squared, is assigned to a variable of a delegate
 type:


What is the purpose of the wwwroot folder?
The wwwroot folder contains static files and compiled assets, such as JavaScript, CSS, and images that your web application needs. Wwwroot is the only folder in the entire 
project that’s exposed as-is to the browser. 

What is the difference between IIS and Kestrel? Why do we need two web servers?
The main difference between IIS and Kestrel is that Kestrel is a cross-platform server. It runs on Windows, Linux, and Mac, whereas IIS only runs on Windows.

Another essential difference between the two is that Kestrel is fully open-source, whereas IIS is closed-source and developed and maintained only by Microsoft.

IIS is very old software and comes with a considerable legacy and bloat. With Kestrel, Microsoft started with high-performance in mind. They developed it from scratch, 
which allowed them to ignore the legacy/compatibility issues and focus on speed and efficiency.

However, Kestrel doesn’t provide all the rich functionality of a full-fledged web server such as IIS, Nginx, or Apache. Hence, we typically use it as an application server, 
with one of the above servers acting as a reverse proxy. 

An action method is a method in a controller class with the following restrictions:

It must be public. Private or protected methods are not allowed. 
It cannot be overloaded.
It cannot be a static method.


What is the difference between early binding and late binding?
Early Binding: In early binding, a non-virtual method is called which is decided at a compile time.

Late Binding: In late binding, a virtual method is called which is decided at runtime.

What are the differences between the Response.Write() and Response.Output.Write()?
Response.Write() is used for normal output whereas Response.Output.Write() is used for formatted output.

What is the use of Global.asax file?
The Global.asax file is used to execute the application-level events and sets application-level variables.

What is event bubbling?
When child control sends events to parent, it is termed as event bubbling. Server controls like Data Grid, Data List, and Repeater can have other child controls inside them.


What is Ajax in ASP.NET?
Answer. Ajax stands for Asynchronous JavaScript and XML; in other words Ajax is the combination of various technologies such as a JavaScript, CSS, XHTML, DOM, etc. AJAX allows 
web pages to be updated asynchronously by exchanging small amounts of data with the server behind the scenes. This means that it is possible to update parts of a web page,
 without reloading the entire page. We can also define Ajax is a combination of client-side technologies that provides asynchronous communication between the user interface 
 and the web server so that partial page rendering occurs instead of a complete page postback. Ajax is platform-independent; in other words, AJAX is a cross-platform technology 
 that can be used on any Operating System since it is based on XML & JavaScript. It also supports open source implementation of other technology. It partially renders the page 
 to the server instead of the complete page being post back. We use AJAX for developing faster, better and more interactive web applications. AJAX uses an https request between 
 web server & browser.

With AJAX, when a user clicks a button, you can use JavaScript and DHTML to immediately update the UI, and spawn an asynchronous request to the server to fetch results.
When the response is generated, you can then use JavaScript and CSS to update your UI accordingly without refreshing the entire page. While this is happening, the form on the 
user’s screen doesn’t flash, blink, disappear, or stall.
The power of AJAX lies in its ability to communicate with the server asynchronously, using a XMLhttpsRequest object without requiring a browser refresh.
Ajax essentially puts JavaScript technology and the XMLhttpsRequest object between your Web form and the server.
[3:48 pm, 18/11/2023] dHrUv SiR(iNnOsTaX): SDLC life cycle
entity framework
Microservices




- SOLID Principles
S -> Single Responsibility Principle
O -> Open/Closed Principle
L -> Liskov's Substitution Principle
I -> Interface Segregation Principle
D ->  Dependency INversion Principle

1. Single Responsibility Principle -> this principle states that a class should have only one responsibility. OR a class should have only 1 reason to change. 

ex. -> if a class  have CalculateSalary and GetDepartment function and Save function in its. then we should keep the same type of functions in a class. like in this calculateSalary 
and GetDepartment funciton are of same type but save is a database related function so we should not keep it in this class.this violates the SRP. we should keep it in repository
class. we should keep the same type of functions in a single class. like we do in our service classes. another example is if we have 3 functions like addiNvoice, deleteInvoice and 
SendingEmail functions in a class. then addiNvoice and deleteInvoice are of the same type and SendingEmail is an extra responsibility on the class. so to follow the SRP we should 
keep the SendingEmail function in the different class. 

Advantage -> if we do have same type of responsibility in a class then it is easy to change and test.


2. Open/Closed Principle ->  this is the second principle.SRP is the prerequisite for Open/Closed principle. software entities like classes, modules should be open for extension but 
closed for modification. for eg. if we want to do some changes in the pre defined class then don't modify it instead try to extend it by creating a new method. 

for eg -> if we have a function a class whcih is calulating interest on different type of accounts saving or current. but  now we also want to calculate the interest for an 
another type of account then we should not update then function but instead we should define the calculateInterest method in the interface and implement those funciton for different 
account type in different classes so this way we can achieve it. 

like -> public interface ICalculateService{
Task<float> CalculateInterest(string accountType);
}

now implement this interface in different classes. 

like  -> public class SavingInterestSErvice : ICalculateService{

public Task<float> CalculateInterest(string accountType){

..... implementation 
}
}

public class CurrentInterestSErvice : ICalculateService{

public Task<float> CalculateInterest(string accountType){

..... implementation 
}

this way we can achieve the Open/Closed principle. benefit of this is simple testing is required to test indivisual classes.

3. Liskov's Substitution Principle -> LSP -> it states that an object of the child class must be able to replace the object of the parent class without breaking the funcitonality 
of the application. 

Defintion -> all the base class methods must be applicable for the child class. this way we can replace the parent class object by child class.

like if we have calculateSalary and CalculateInterest method in the base class then they should be available to the child class and instead of using the parent class object we can 
call them by calling the child class object.

4. Interface Segregation Principle -> It states that a class should not be forced to implement the interface that its not use. 
for eg -> if an interface ccontains 2 functions driveCar and driveBus and a class is implementing this interface but in that class we need driveCar but don't need to driveBus
function then in that case it is necessary for the class to implement all the functions of the interface but class don't need it. then in such scenarios we should create the
different interfaces for the driveCar and drivebus functions. and now if class wants the driveCar function then the class can only implement the driveCar interface and in future 
if the class also want to implement the driveBus funciotn then can use that interface so this way we can also achieve the multiple inheritance. 

so according to this principle it is better to have smaller smaller interfaces instead of the large interfaces.

5. Dependency Inversion Principle -> It states that a high level class must not depend upon a child level class..

for eg: we have a class

public class DataAccessLayer{
public void AddCustomer(string name)
{
FileLogger fileLogger = new FileLogger();
fileLogger.Log("Customer : {name} added");
}}

now in the above example the DataAccessLayer is completely dependent upon FileLogger class. if we need to change the FileLogger class and need to use the DatabaseLogger class
then we need to update it in all the classes wherever it is used in the class. it is called tight coupling. 

Now to remove that we have Dependency Inversion principle and Dependency Injection is used to implement the Dependency Inversion principle.

in that case 

we should create an interface for the Log method like

public interface ILogger{
void Log(string message);
}

public class FileLogger : ILogger 
{
public void Log(string message)
{
// implemnation 
}
}
 
 and now ni the DataAccessLayer inject the Ilogger interface object
 
 public class DataAccessLayer{
  public  ILogger _logger;
  public DataAccessLayer(ILogger logger){
  _logger = logger;}
  
  public void AddCustomer(string message){
  _logger.Log("Customer : {name} added");
  }
 }
 
 
- What is the difference between Solid principle and Design Patterns? 
Solid principles are a set of principles, which must be followed to develop flexible, mainatainable and scalable software systems. 
whereas the Design Patterns are concrete and solve particular kind of problems in softwares. 

solid principles should must be there in an application but design patterns are optional as they resolve only particular kind of problems and if we don't have those problems then 
no need to use design patterns. 



var configurations = new ConfigurationBuilder().AddbasePath(Directory.GetCurrentDIrectory()).AddJsonFile("appsetting.json", reloadOnChange: true).AddJsonFile().AddEnvironmentVariables()
.Build();
[3:49 pm, 18/11/2023] dHrUv SiR(iNnOsTaX): -> explain the mvc pattern in asp.net. how does it work, and what are the advantages.
MVC is an architectural design pattern. it divides the application into 3 components 
i.e Model, View and Controller

Model -> Model is the first component of the MVC pattern and it contains the business logic and the application's data. Model is use for all the database operations like 
processing, fetching and storing the data. Models are the database related objects such that classes that represents tables in a database. 

View-> View is the second component and it is responsible for the UI part. it responsible for presenting the data to the user. In asp.net they are 
essentially the html templates that displays information to the user. in asp.net, these are typically .cshtml(razor pages) or .aspx files. 
- They interacts with the controller on a specific user action.

Controller -> The controller acts as an intermediary between the view and the model to perform actions and then selects the appropriate view to render the response.
Controllers handles user inputs and use model to process the input(if required) and then sends that data to the view.
Controllers defines the application's routing, receives http requests and returning the appropriate http response. 

how MVC works in Asp.net -> 
firstly a user initiates an http request like enters the application's url. the routing system in the asp.net routes the request to the controller based on the route. 
then the controller processes the request and will interact with the model(if required) and choose the view to render the response and provides that necessary data to the 
view. now the view takes the data and create the html template which we need to show on the UI. and sends back to the browser. now the browser displays the HTML, and the user  
can interact with the web application. 

Advantages of MVC -> 
1. Seperation of Concerns -> the mvc pattern enforces a clear seperation of concerns, making it easier to maintain and test different aspects of the application indepedently. 
in this the MVC patterns seperates the responsibility of the Model, View and Controller components. ensuring that each component focuses on its specific role without interfering
any other's work. 

2. Testability -> Each component can be tested indepedently. this facilitates unit 
 and makes it easier to find and fix the bugs.

3. Reusability -> Components in MVC are reusable and they often can be resused in different parts of the applications. for eg. a model can be used in multiple components. this makes 
the more efficient and modular code.

4. Scalability -> as the application grows, MVC can help manage complexity and keep the codebase organized.

5. URL Routing -> ASP.net MVC includes a powerful routing system that allows for clean and user-friendly routing, enhancing SEO and user-experience. 

-> what is asp.net core, and how dies it differ from traditional asp.net. what are the architecture changes in asp.net core?
-> Describe the concept of middleware in asp.net core. how it used to handle requests and response. 
Middleware is the key component of the Asp.net core applications, which handles the incoming http requests and responses as they flow through the application's processing pipeline. 
middleware is a set of components that are executed sequentially, and each component performs a specific task in processing an HTTP request and generating an http response. 
Here's how middleware works and is used to handle the HTTP requests and responses in ASP.net core.
- Middleware Pipeline -> asp.net core application have a middleware pipeline that is constructed in the startup class. the pipeline defines the order in which middleware components
are executed. components can be added to the pipeline using the use method. 

- Order Of Execution -> the components in the middleware are executed  in the order they are added in the pipeline. the request enters the pipeline and each middleware component 
processes it or performs some actions. and then the response flows back through the  pipeline in the opposite order of execution. 

Middleware components are used for authentication, routing, logging and response compressions and more. 

-  what is dependency inject and how is it implemented in asp.net vcore for managing application components?

- explaing the purpose and use of the startup class in an asp.net core application
- discuss the difference between state management techniques in asp.net, including viewstate, session and cookies. when would you use each of them 
here are the top 3 state management techniques in asp.net application 
- ViewState, Session and Cookies

ViewState -> ViewState is a client-side state management technique in asp.net. and used to persist small amount of data between postbacks, primarly for maintaining 
the state of controls on a single page. 
Use ViewState when  u need to maintain the control state withing a single page and when the data is small and not sensitive. if u use viewState for larger page sizes, then it will 
lead to the more page load times. 

session -> session is the server-side state management technique in asp.net. it is used to persist user-specific data for the duration of a user's visit to the application. and 
data stored in state can shared among multiple pages for the samee user. it stored on the server and server keeps SessionId cookie on the client to link the client to the 
data. use state when u need to store user specific data, such as cart items, user authentication. 

Cookies -> cookies are a client side state management technique. they are small peice of data that are stored in the user's browser, which can be used to persist data 
across requests. they are used to track the user behaviour and they are browser dependent. Use cookies that should servive across sessions and even after the user
closes the browser.

- how do u implement authentication and authorization in asp.net application can u explain the difference btween authentication and authorization.
authentication and authorization are the 2 aspects of security in asp.net applications.
authentication is to verifying the identity of the user means who are you? it typically involves to verifyin the user credentials.
authorization is to determine what actions or resources you can access. means what are you allowed to do? 
authentication can be implement through the below steps: 
- WIndows authentication, forms based authentication, identity providers(google, facebook), tokens authentication, api key authentication
authorization can be achieved by using:
Role based authorization, Policy-based authorization, Attibute based authorization like [Authorize]

- describe the benefits and drawbacks of using entity framework for database access in an asp.net application
entity framework is a popualar ORM(Object Relational Management) framework provided by microsoft for database access in asp.net applications. 

- what is RESTful architecture and how does asp.net web api support it

- explaing the concept of caching in asp.net. how and when would use the caching to improve application performance
caching is a technique used in asp.net applications to store and retrieve frequently accessed data, processed results which reducing the need to repeatedly fetch or 
regenrates the same data from the source. caching is used to improve the application performance, improving response times and decrease the load on backend resources. 
Types of Caching:
- output Caching -> output cache stores the generated html content of a page or a user control. it allows the entire rendered output to be cached for a specific duration or 
based on specific criteria. 
- Data Caching -> data caching involves caching the result of sql queries, computed values, or the response from external api's.
- Fragment Caching-> Fragment caching enables u to cache specific parts of a page rather than the entire output. 
- Custom Caching -> Asp.net allows Custom Caching, where u can store and manage any data in memmory for a specific duration. this is used for complex scnearios. 

When to use Caching -> 
Frequently accessed data -> which is accessed frequently but not changing frequentlly.  
Expensive Operations -> if the process if expensive or time taking then we can use caching. 
Reducing database load -> can reduce the load on database by storing frequently query results in memory.
Improving response time

Considerations and Best Practices:

Cache Expiration: Be mindful of cache expiration times. You should set an appropriate duration based on the data's volatility. You can also use cache dependencies to 
automatically invalidate cached data when the source changes.

Cache Invalidation: Ensure that the cache is invalidated (cleared) when data is updated or changes. Stale data can lead to incorrect results.

Memory Usage: Be cautious of excessive memory usage. Caching can consume memory, so you need to strike a balance between improving performance and resource consumption.

Vary by Parameters: When using output caching, consider varying the cache by parameters to ensure that different versions of a cached page are maintained based on user-specific 
or context-specific factors.

- how can you optimize the performance of an asp.net application and what tools or techniques would use use for profiling and debugging
 CodeOptimization -> minimize database queries, use efficient ds and algorithms
 Caching
 Content Delivery -> Utilize Content deliver networks 
 Code Reviews -> and refactor the codebase required
 WEb server and database optimization
 
 
- what if the role of global.asax file in asp.net application 
 in asp.net applications the global.asax file is also known as global application class. which plays a very important role in managing and handling application 
 level events. it is an optional file which gets created automatically when an application gets created. 
 this file is writeen in C# or VB.NEt and contains the event handler methods like application_Start, end and session_Start and end. 
 
1. Application Events -> Application_Start -> it gets triggered when the application starts and its better to perform one-step tasks, which we need to do on starting the application.
Application_End-> it got triggered when the applications ends. its better to keep the resource releasing or perform cleanup operations code in this block..

2. SessionEvent -> Session_Start -> this triggeres when a new session gets starts for a new user. u can perform user-specific tasks in it like authorization and authentication.
Session_end -> when the session gets end then it gets used and can be used for session cleanup.

3. Error Handling -> Application_Error -> this event is triggered when an exception is occured inside the application u can use it to log errors, send notifications to the admin and 
other tasks.

4. Custom Events -> we can also create custom methods and events in the global.asax file to handle the application specific tasks that needs to execute at the application level.
5. Application Configuration -> u can access and modify application-level configurations settings in the global.asax file.

but when the asp.net core came into the picture the global.asax file is not used, and application level events are typically handled through the startup file. but in traditional 
asp.net applications, the global.asax file was used for applicatoin level configurations.
 
 
- discuss various deployment strategies for asp.net applications, including considerations for scalability and high availability.
- explain the concept of microservices architecture and how asp.net can be used in a microservices environment
- what are the security best practices in asp.net, including techniques to prevent commong vulnerablities like sql injection and cross site scription(XSS) ? 


QUEE  ----> What is the difference between ASP.NET Web Forms and ASP.NET MVC, and when would you choose one over the other for a web application?
ASP.net webforms and asp.net mvc both are the different techniques to build the web applications in ASP.net framework. 

- ASP.net web forms follows a traditional event-driven development model.  whereas ASP.net is a lightweight MVC pattern based development model.
- ASP.net web forms has file based url's means the file exists in the URLs must have its physical existence. whereas ASP.net has route based URLs means URLs are divided
into controllers and actions and moreover it is based on controller not on the physical files.
- ASp.net webforms has user controls for code-resuablitiy whereas asp.net mvc has partial views for code-resuablitiy. 
- In Asp.net webforms, web forms(ASPX) i.e View are tightly coupled with the code behind files.(.aspx.cs) and in asp.net mvc views and logic are kept seperately.
- ASp.net web forms in not open source whereas mvc is open source. 

QUE ------> Explain the SOLID principles and how they relate to C# development.
SOLID PRinciples explained alreaady and they are used in C# development. 

QUE -------> What is the role of the Model-View-Controller (MVC) pattern in C# applications, and how does it contribute to application architecture?
MVC same and contribution -> In summary, the Model-View-Controller (MVC) pattern in C# applications contributes to a well-structured, organized, and maintainable architecture 
by separating concerns, promoting modularity, improving testability, and enhancing the flexibility and reusability of components. It provides a solid foundation for building 
complex and robust applications.

Quee ------> Can you explain the concept of Dependency Injection and provide an example of how it is implemented in C#?
Dependency Injection is a design pattern in C# that promotes loose coupling between components in a software system. it is a technique used to manage the dependencies by 
injecting them into the classes rather than having their dependecies directly. 
If we are implementing the IStudentservice in StudentService then it gives the facility to change the IStudentservice without affecting the StudentService class.

Que --------> How does asynchronous programming work in C#, and when is it beneficial to use async/await in application architecture?
- asynchronous programming in C# allows u to write code that can perform multiple operations simultaneously, without blocking the main execution thread. Asyncronous programming 
can be achieved by using async await keywords in c#. 
here's how it works:

- async -> to make a method asynchronous we need to use the async keywork in the method definition. it tell the compiler that this method  can contain asynchronous operations.

- await -> 	we can use the await keyword only in the async function. and it is used to pause the execution of that method until the awaited operation is completed. 

- Task and Task<T> -> Asyncronous methods often returns Task objects which represents operations that can be awaited. Task<T> is used when any function is returning any value and 
if the method doesn't return anything then we use Task.

- Non-Blocking-> while an async method is waiting for an asynchronous operation to complete, it doesn't block the main thread. this allow other code to run concurrently. 

- Continuation -> when the awaited operation completes, the async method resumes execution from the point of the await keyword. 


Benefits of using async/await in application - 
Improved Responsiveness, Better scalability, Parallelism, Improved User experience, Reduced Waiting time

when to use async/Await -> I/O Bound operations, Long Running tasks, Parallelism, datbase operations 

Que -----> Discuss the difference between REST and SOAP, and explain when you would choose one over the other for designing web services in C#.

What is the .NET Core (now .NET 5+) framework, and how does it differ from the .NET Framework in terms of application architecture?

Describe the concept of microservices architecture and how C# can be used to build microservices-based applications.

How does Entity Framework fit into C# application architecture, and what are the advantages and limitations of using an Object-Relational Mapping (ORM) tool like Entity Framework?

What is the purpose of the ASP.NET Web API, and how can it be used to build RESTful services in C#?

Explain the concept of design patterns, and give examples of design patterns commonly used in C# development.
design patterns are resuable solutions  to common problems that arise during  software development. they provide a template for solving those architectural and structural 
issues in a systematic and efficient way. some commonly used design patterns are:
- SIngleton Pattern, MVC pattern, Repository pattern 

Discuss the role of caching in application architecture. How can you implement caching in a C# application, and what are the benefits of caching?

What are the key considerations when designing a high-performance and scalable C# application architecture, especially in a web-based environment?
Here are the key considerations while designing a high-performance application
- Understand the requirements, Choose the right architecture, Load Balancing, Horizontal scaling, Caching, Asyncronous Programming, Database design, efficient code, statemanagement

Explain the differences between stateless and stateful communication in web applications, and how you would choose between them in your C# application architecture.

How can you ensure security in C# application architecture, especially in web applications? Discuss common security measures and best practices.
-Authentication  and authorization
- input validations
- Session Management
- Configure CORS policy
- Logging and Monitoring

What is Continuous Integration (CI) and Continuous Deployment (CD), and how do they contribute to the architecture and development process in C# applications?

Describe the concept of containers and containerization, and how tools like Docker can be integrated into C# application architecture.

Discuss the importance of unit testing and integration testing in C# application architecture. What are some popular testing frameworks in the C# ecosystem?

Explain the concept of code maintainability and scalability in C# architecture, and discuss strategies for keeping codebases clean and extensible.

Can you provide an example of a real-world C# application architecture you've designed or worked on, highlighting the key architectural decisions you made?

'''''''''
-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### CI/CD
Are software development practices which makes the development, testing and deployment process easier for any application. these processes plays an important role in 
the architecture and development processes of C# applications as well as in software deployments more broadly.  

CI/CD pipeline is a set of automated processes and tools used in software development to ensure that code changes are built, tested and deployed quickly and consistently. 

### CI -> 
Continuous Integration focuses on the process of frequently integrated code changes from multiple devs into a shared repository. the main task is to detect and address 
integration issues early and ensure that the application is always in a working state. 

### steps in CI process: 
### Code Commits -> 
whenever any developer commit their changes in the version control system e.g Git. this triggers the CI process. 
### Automated build -> 
the CI server automatically builds the code to ensure there is not any compile error and the code is successfully compiled.
### Automated Testing -> 
if the code build successfully then the automated testing like unit testing or automate testing starts to identify the bug. 
### Immediate Feedback -> 
Developer receives immediate feedback on the status of their code changes, such as whether the builds and tests are successful.
### code commits -> 
automated builds -> Automated Testing -> Code Quality Checks -> Immediate Feedback 

### CD -> Continuous Delivery/ Deployments -> 
its primarly focuses on the automating the deployment to various environments. such as development, staging and production. 
the primary goal is to reduce the overhead in deployments, ensure consistency between environments. 

#### CD -> 
After the CI process executed successfully it produces artifacts such as compiled COde, Configuration files and other resources. 
Deployment Automation -> CD tools automate the deployment process, taking the artifacts and deploying them to various environments, including qa, staging and production.
Environment Configuration -> CD systems manage environment specific configuration, ensuring that each environment is properly setup.
Rollback Mechanisms -> CD pipelines often includes mechanisms to rollback to a previous stage if any issue occurs in the production environment.
Monitoring and Logging -> after deployment, monitoring and logging tools help track the application's performance and detect issues.

Pipeline Stagess -> each CI/CD process consists of multiple stages, such as built, test, deploy and monitoring. each stage has specific tasks and checks that ensure the 
quality reliability of the code.

### Benefits of CI/CD ->
Faster Development -> it enables programmers to writing code rather than managing deployments and testings.
Improved Quality -> automated testing and continuous integration catch issues early in the development process,so it improves code quality.
Consistency -> CD ensures that teh applications are deployed consistently on all the environments where it reducing the 'its working on my computer problem'.
Faster Delivery -> CD enables faster delivery of the new features and bugs in the softwares.  

CI/CD pipelines can be implemented using various tools and services, including Jenkins, Travis CI, CircleCI, GitLab CI/CD, and cloud-based services like AWS 
CodePipeline and Azure DevOps. The choice of tools depends on the specific needs and technologies of the project.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### Testing -> 
Testing is the process to test the functionality for which the function was originally created. it's the most important part of the software. Testing is of 2 types:
Manual testing, Automation Testing

#### Manual Testing -> 
Manual testing is the process of testing to test the functions manually. in this we do call the functions and then test their functionality. it is very much 
time taking process. To avoid the testing automate testing came into the picture. 

#### Automation testing -> 
Automation testing is the process of testing the functionality of the function automatically. in this we do test our functions by writing the codebase. it is
much faster than the manual testing. Automation testing is of 3 types mainly.

1. Unit Testing 
2. Integration Testing 
3. End to End Testing

### Unit Testing -> 
Unit testing is a part of the automation testing. in this we do test the functionality of the small small components. unit testing is done without the external 
dependencies like if we do have any external dependecy in our codebase then it will not performed. like database operations or any other file read/write operations. these will not
cover into the unit testing. due to this behavious it is very fast. Unit tests focus on the correctness of individual units of code

### Integration Testing -> 
Integration testing is the 2nd part of the Automation testing. in this we do overcome the unit testing and also does the testing of the external dependecies.
it is slower than the unit testing because in this we do test the external dependecies too.  integration tests verify that these units work together seamlessly.

### End-To-End Testing -> 
end 2 end testing means when we do test the functionality from the UI. we do test the frontend and backend functionality in this. It takes higher time than 
all of the others. and this testing is done from the end user perspective. we need to run the application and then login and then test the functionality from the user 
perspective. 

now the question is which we should prefer in our application. we should prefer all of them in our application according to our requireemnts.

we do have a PyramidTest principle which is used to explain the testing phases. 


Unit Testing-> in any app we should done unit testing first. it is used to test the switch cases and logics of your codebase but it doesn't test the external dependencies of the 
app. it is the fastest testing we can done in any app.

Integration Testing -> integration testing can be perform after the unit testing and it do contains the external dependecies testing in itself. it takes more time than the unit 
testing. 

End-To-End Testing -> E2E testing is performed to test the functionality of the complete app from user point of view. in this we do test the frontend and the backend 
functionaltiy of the app.

we do have many tools to perform this automation testing. like Nunit, MSTest, xUnit and many others. 

### Now the question is how do we perform the unit testing -> 
To perform the unit testing we do write the test cases which will get execute during the automation testing. we can do 
this by creating a new project and a new class in that project now in this class at the top there will be an attribute named TestClass and in this we will define the test cases 
in the  methods form and all the methods will have the TestMethod attribute on the top. in this if we want to write the test case for a methodd which can have 3 scenarios in that
function then we will write 3 test cases for that function and will perform these test cases. 


### Now ->
If u are dealing with automation testing then there is a term named TDD -> Test Driven Development now according to this we write the test cases first for any code and then 
will write the code on which these test cases will be performed. but the question is how can we do that? how can we write the test cases for a code which is not written yet. so 
for this we have three steps in this process:

1. Write a failing test
2. Write the minimal code which can pass this test
3. Refactor the codebase if required

all these steps will be performed in the TDD. the advantages of this is our code will always be the testful and for this we don't need to worry that if our code is tested or not.

### Unit TEsting -> 
Unit Testing is a testing pattern in which individual components or units of a software application are tested in isolation to ensure that they are working as 
intended. the term unit typically refers to the smallest testable part of the code, which could be a function, method or class. 

### Characteristics of the Unit Testing -> 
1. Isolation -> unit testing is designed to test the specific component in isolation. 
2. Automation -> Unit tests are automated, meaning they are written as code, and testing frameworks or tools are used to execute them. Automated testing ensures that testing 
can be run consistently and repeatedly.
3. Independence -> each unit test should be independent of other, meaning that the outcome of one unit test should not affect the result of another. 
4. Immediate feedback -> Unit test provide immediate feedback to developers. when a test fails , it immediately tells the develper that the code is not working properly.
5. Regression Testing -> unit tests are often used for unit testing. when code changes are made, running unit tests ensures that existing functionality is not broken.

Unit testing is an essential part of the software development process, as it contributes to code quality, maintainability and reliability.


------------------------------------------------------------------------------------------------------------
###  Microservices is an architectural design pattern in which we divides the large/Monolithic application into small-small, indepently deployable services. each service focuses on 
a specific piece of functionality and operates as a standalone unit within a larger ssystem. this architecture is designed to improve the flexibility, scalability and 
maintainability of the software applications. 

### Some key points about Microservices -> 
1. Independence ->  each microservice has its own codebase and its own database. this means u can update, deploy and maintain one microservice without affecting any other service.
2. Communication -> Microservices communicate with each other using APIs, typically through REST api's. this allow them to work together to provide a complete functionality for an app.
3. Scalability -> Microservices can be scaled independently based on their specific workload. 
4. Development Teams -> Each microservice is developed by a seperate team, this enables the parallel development and faster feature delivery.
5. Technology Diversity -> Different Microservices can use different programming languages or technologies. for example, some microservices might be written in c#, while others use 
Java, python or any other language.
6. Rapid Deployment -> Microservices are indepedently deployable, allowing changes to be deployed quickly within the application.
7. Fault Isolation -> Failures in one microservices does not impact any other microservice as they are independent to each other.
Testing -> Microservices can be tested independently, which facilitates unit testing, integration testing.  

### Microservices -> 
microservices is the collection of the multiple services. Services are the web api projects in .net. 

Microservices is a small unit that has only  1 responsibility or single logic which solves a specific problem.
Microservices are small and independent services that work together to build highly automated, independent and evolving softwares. 

here the note is don't get confused with the word services becuase it doesn't mean it must be a service microservice can be a frontend unit or backend unit and microservice can 
be build in any language in .net, java or nodejs. u can build microservices in any of the language. 

### Advantages -> 
Language Independent and framework independent.
- Support independent development, deployment and versioning.
- Even we can scale them in seconds without compromising the integrity of the application.
- Better fault isolation and it doesn't halt the working of any other service. 
- Zero downtime upgrades.
- Supports CI/CD.


### What iss the Monolithic vs N-Layer/SOA vs Microservices architecture?
- In monolithic we have the single unit and in that unit all the code is present then in NLayer/SOA in this we do have multiple units instead of single like 4 units instead of 
the single monolithic unit. and then in microservices architecture we do have multiple small small units are called microservices. 

for eg : if we have a single unit in monolithic then we will have 4 units in N-Layer/SOA and then we will have 20 units in microservices.

### Microservices Priciples -> 
we do have some principles while defining the microservices and here they are:
1. Modelled around Business Domain -> before creating the microservices we should know about the different domains of the application on which we are working. and accordding to 
those domains we will create seperate-2 microservices. for eg we have an application for a banking system then in that we will create microservice for creating accounts,, another 
microservices for handling the Debit transactions and credit transaction.

2.Culture of Automation ->  To build a microservice in a better way so that we can automate its deployment and configuration we need to implement the devOps and with the help 
of devOps we can automate these operations.

3. Hide Implementation Details -> as we can have the microservices in many application so these microservices should hide their internal implementation always.

4. Decentralize all the things -> In our traditional applications we try to centralize the database where we use only 1 database. but in microservices we should use the decentralize 
approach and in this all the microservice have different databases. 1 or 2 microservice can have same database but not more then 2 or 3 should use the same database. 

5. Deploy Independently -> As they are working indepedently and they are more decentralized then we can easily deploy the applications easily if they are self contained like they 
don't need any other. so that way we can easily deploy them independently with the help of CI/CD pipeline.

6. Isolate Failure ->  if one of the microservice is failing so it should not impact the other microservice so we should design the service in a way that failure of one doesn't 
impact the other one.

7. Highly Observable -> A microservice should contain all the necessaary information so that if in case any microservice got break  so than we can easily troubleshoot the problem.

### when to use microservice architecture? 
not useful in every architecture becuase they are little bit difficult then the other, we should use it where:
- large applications that require a high release velocity
- Complex application that need to be scalable


### Challenges of Microservices
- COmplexity -> more complex
- Development and testing ->
- Lack of governance 


### Explain Microservices architecture -> collection of multiple services and unified by the api gateway. the client will send the request to api gateway and then api gateway 
will interact to the services. these services interact with each other by Event Bus. 

### How will u transform an N-layer app to Microservices app?
- suppose if we have an app which contains a database and it has a business layer in which it has 3 components like Catalog, Authentication and order. and we have a UI for this
website. now when we convert it into the microservice architecture then there will be 3 microservices named Catalog Microservice, Authentication Microservice and Order 
microservice. and all of them have their own seperate database. they will communicate with each other using EventBus.  and will have a UI.

###What are microservice orchestration?
- 
### What are microservices deployment options in Cloud?
- on Azure cloud we do have Azure AKS, Service fabric 

- Various design patterns for Microservices?
1. Decomposition Pattern - Decompose by business capablility
- Decompose by subdomain
- Strangler Pattern 

Integration Pattern, Database Pattern, Communication Pattern, Cross Cutting Concerns Pattern, Observability Pattern, Deployment Patterns

