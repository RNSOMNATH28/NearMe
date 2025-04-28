# Ex04 Places Around Me
## Date: 

## AIM
To develop a website to display details about the places around my house.

## DESIGN STEPS

### STEP 1
Create a Django admin interface.

### STEP 2
Download your city map from Google.

### STEP 3
Using ```<map>``` tag name the map.

### STEP 4
Create clickable regions in the image using ```<area>``` tag.

### STEP 5
Write HTML programs for all the regions identified.

### STEP 6
Execute the programs and publish them.

## CODE
```
views:
from django.shortcuts import render

def triangle_area(request):
    area = None  # Initialize area to None for the first load
    if request.method == "POST":
        try:
            base = float(request.POST.get("base"))
            height = float(request.POST.get("height"))
            area = 0.5 * base * height  # Calculate the area
        except ValueError:
            area = "Invalid input. Please enter numeric values."
    
    return render(request, "triangle_area.html", {"area": area})
```
```
url:
from django.contrib import admin
from django.urls import path
from app import views

urlpatterns = [
    path('admin/', admin.site.urls),
     path('area/', views.triangle_area, name='triangle_area'),
]

```
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Triangle Area Calculator</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Libre+Baskerville:wght@400;700&display=swap');

        body {
            font-family: 'Libre Baskerville', serif; /* Royal font style */
            margin: 0;
            padding: 0;
            background: linear-gradient(135deg, #8e44ad, #3498db, #f1c40f);
            background-size: 300% 300%;
            animation: gradientBG 6s ease infinite;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            color: #fff;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .container {
            text-align: center;
            padding: 20px;
        }

        h1 {
            font-size: 2rem;
            margin-bottom: 30px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.6);
        }

        label {
            font-size: 1.1rem;
            font-weight: bold;
            margin-bottom: 10px;
            display: block;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.4);
        }

        input {
            background: rgba(255, 255, 255, 0.9);
            border: none;
            border-radius: 10px;
            width: calc(100% - 30px);
            padding: 12px 15px;
            margin: 10px 0;
            font-size: 1rem;
            color: #555;
            text-align: center;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.2);
        }

        button {
            background-color: #e74c3c;
            color: white;
            border: none;
            padding: 12px 25px;
            margin-top: 20px;
            border-radius: 10px;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
            transition: transform 0.2s, background-color 0.3s;
        }

        button:hover {
            background-color: #c0392b;
            transform: scale(1.05);
        }

        .box {
            margin: 15px 0;
            padding: 20px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.3);
            backdrop-filter: blur(5px);
        }

        h2 {
            color: #f1c40f;
            margin-top: 20px;
            text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.6);
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Triangle Area Calculator</h1>
        <form method="post">
            {% csrf_token %}
            <div class="box">
                <label for="base">Base:</label>
                <input type="number" id="base" name="base" step="any" required>
            </div>
            <div class="box">
                <label for="height">Height:</label>
                <input type="number" id="height" name="height" step="any" required>
            </div>
            <div class="box">
                <button type="submit">Calculate Area</button>
            </div>
        </form>
        {% if area is not None %}
            <h2>Area of the Triangle: {{ area }}</h2>
        {% endif %}
    </div>
</body>
</html>
```

## OUTPUT
## SERVER SIDE PROCESSING
![image](https://github.com/user-attachments/assets/4a755148-6f1d-4af2-9c54-22e1f576990e)
## HOMEPAGE
![image](https://github.com/user-attachments/assets/110962ec-98c3-491f-81fb-cdb67550eb06)
## RESULT
The program for implementing image maps using HTML is executed successfully.
