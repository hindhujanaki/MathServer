# Ex.05 Design a Website for Server Side Processing
## Date:02.04.2024

## AIM:
To design a website to find surface area of a Right Cylinder in server side.

## FORMULA:
Surface Area = 2Πrh + 2Πr<sup>2</sup>
<br>r --> Radius of Right Cylinder
<br>h --> Height of Right Cylinder

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create python programs for views and urls to perform server side processing.

### Step 5:
Create a HTML file to implement form based input and output.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```
## math.html

<html>
<head>
<meta charset='utf-8'>
<meta http-equiv='X-UA-Compatible' content='IE=edge'>
<title>Area of surfacearea</title>
<meta name='viewport' content='width=device-width, initial-scale=1'>
<style type="text/css">
body 
{
background-color:rgb(212, 255, 0);
}
.edge {
width: 1440px;
margin-left: auto;
margin-right: auto;
padding-top: 250px;
padding-left: 300px;
}

.box {
display:block;
border: Thick dashed rgb(0, 255, 30);
width: 500px;
min-height: 300px;
font-size: 20px;
background-color:rgb(255, 192, 213);
}

.formelt{
color:rgb(0, 221, 255);
text-align: center;
margin-top: 7px;
margin-bottom: 6px;
}

h1
{
color:rgb(255, 47, 0);
text-align: center;
padding-top: 20px;
}

</style>
</head>
<body>
<div class="edge">
<div class="box">
<h1>Area of surfacearea</h1>
<form method="POST">
{% csrf_token %}
<div class="formelt">
Radius : <input type="text" name="radius" value="{{r}}"></input>(in m)<br/>

</div>
<div class="formelt">
Height : <input type="text" name="height" value="{{h}}"></input>(in m)<br/>
</div>
<div class="formelt">
<input type="submit" value="Calculate"></input><br/>
</div>

<div class="formelt">
Area : <input type="text" name="area" value="{{area}}"></input>m<sup>2</sup><br/>
</div>
</form>
</div>
</div>

</body>
</html>

## views.py

from django.shortcuts import render
def surfacearea(request):
    context={}
    context['area'] = "0"
    context['r'] = "0"
    context['h'] = "0"
    if request.method == 'POST':
        print("POST method is used")
        r = request.POST.get('radius','0')
        h = request.POST.get('height','0')
        print('request=',request)
        print('radius=',r)
        print('height=',h)
        area = 2 *3.14*int(r) * int(h) + 2*3.14*int(r)*int(r)
        context['area'] = area
        context['r'] = r
        context['h'] = h
        print('Area=',area)
    return render(request,'mathapp/math.html',context)

## urls.py

from django.contrib import admin
from django.urls import path
from mathapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('surfacearea/',views.surfacearea,name="surfacearea"),
    path('',views.surfacearea,name="surfacearearoot")
]


```

## SERVER SIDE PROCESSING:

![Screenshot 2024-04-08 073612](https://github.com/hindhujanaki/MathServer/assets/148514666/622282d2-b7f1-4df4-90b2-35ce4f61aa98)





## HOMEPAGE:

![Screenshot 2024-04-08 073833](https://github.com/hindhujanaki/MathServer/assets/148514666/b8f71542-12e6-4336-bb3a-02ebbd35a6a5)










## RESULT:

The program for performing server side processing is completed successfully.
