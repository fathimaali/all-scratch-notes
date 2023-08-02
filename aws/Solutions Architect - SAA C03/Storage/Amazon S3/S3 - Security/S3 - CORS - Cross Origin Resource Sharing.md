![[Pasted image 20230505121625.png]]

![[Pasted image 20230505121800.png]]

![[Pasted image 20230505121940.png]]

fetched from diff bucket in diff region : 

![[Pasted image 20230505123706.png]]

the CORS bucket from where things are being fetched should have CORS enabled for the origin : 

[
    {
        "AllowedHeaders": [
            "Authorization"
        ],
        "AllowedMethods": [
            "GET"
        ],
        "AllowedOrigins": [
            "<url of first bucket with http://...without slash at the end>"
        ],
        "ExposeHeaders": [],
        "MaxAgeSeconds": 3000
    }
]



