<div align="justify">

# BingoCTF - Speedrun Write-up (Challenge Creator: @Cofastic)

> “I was at an incredible pace during my Minecraft RSG Any% speedrun. But amidst the excitement, I completely blanked on the stronghold coordinates I found. I know I uploaded the footage somewhere online under my handle @Cofastic, but I can't remember which platform I used. The run was so good, I made sure to preserve it somewhere safe where it won't disappear forever. Can you help me track down those coordinates?”

**Flag Format:** `BINGOCTF{coordinateX_coordinateZ}`

---

Based on the question description, I am looking for “footage” containing coordinates of the minecraft stronghold uploaded by @Cofastic.  

This is a very simple search for a video uploaded online. Hence, I started my search on common video uploading sites like YouTube, Twitch, etc…  

Going through these websites, I eventually found two Minecraft videos uploaded by Cofastic on the Internet Archive.  
 
Inside these two videos, I can see the player throwing an “Eye of Ender” at two different coordinates.  

- **Location 1:** X = 0.435, Z = 0.773, Yaw = -112.2 degree  
- **Location 2:** X = 350.362, Z = -0.261, Yaw = -116.6 degree  

After obtaining the coordinates, and Yew. Use a stronghold calculator online to calculate the exact location.  

The final location is (1880, -766). 

Hence the Flag is `BINGOCTF{1880_-766}`

</div>
