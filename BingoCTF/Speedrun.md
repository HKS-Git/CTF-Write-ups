<div align="justify">

# BingoCTF - Speedrun Write-up (Challenge Creator: @Cofastic)

<div align="center">
<img src="./assets/Speedrun/Question.png" 
     alt="Question Description" 
     style="display: block; margin: 0 auto;" 
/>
</div>

> “I was at an incredible pace during my Minecraft RSG Any% speedrun. But amidst the excitement, I completely blanked on the stronghold coordinates I found. I know I uploaded the footage somewhere online under my handle @Cofastic, but I can't remember which platform I used. The run was so good, I made sure to preserve it somewhere safe where it won't disappear forever. Can you help me track down those coordinates?”

**Flag Format:** `BINGOCTF{coordinateX_coordinateZ}`

---

Based on the question description, I am looking for “footage” containing coordinates of the minecraft stronghold uploaded by @Cofastic.  

This is a very simple search for a video uploaded online. Hence, I started my search on common video uploading sites like YouTube, Twitch, etc…  

Going through these websites, I ended up on the Internet Archives and searched for the user "Cofastic" with its advance search function. Eventually found two Minecraft videos uploaded by Cofastic on the Internet Archive.  

</div>
<div align="center">
<img src="./assets/Speedrun/VideosFound.png" 
     alt="Ccalculate coordinates using online tool" 
     style="display: block; margin: 0 auto;" 
/>
</div>

Inside these two videos, I can see the player throwing an “Eye of Ender” at two different coordinates.  

<div align="center">
<img src="./assets/Speedrun/Location1.png" 
     alt="Coordinate of Location 1" 
     style="display: block; margin: 0 auto;" 
/>
</div>

- **Location 1:** X = 0.435, Z = 0.773, Yaw = -112.2 degree

<div align="center">
<img src="./assets/Speedrun/Location2.png" 
     alt="Coordinates of Location 2" 
     style="display: block; margin: 0 auto;" 
/>
</div>
 
- **Location 2:** X = 350.362, Z = -0.261, Yaw = -116.6 degree  

<div align="center">
<img src="./assets/Speedrun/StrongholdCalculator.png" 
     alt="Question Description" 
     style="display: block; margin: 0 auto;" 
/>
</div>

After obtaining the coordinates, and Yew. Use a stronghold calculator online to calculate the exact location.  

<div align="center">
<img src="./assets/Speedrun/CalculatedCoordinates.png" 
     alt="Calculate coordinates using online tool" 
     style="display: block; margin: 0 auto;" 
/>
</div>

The final location is (1880, -766). 

<div align="center">
<img src="./assets/Speedrun/SpeedrunQuestion.png" 
     alt="Question Description" 
     style="display: block; margin: 0 auto;" 
/>
</div>

With that I found the flag to be `BINGOCTF{1880_-766}`

</div>
