![image](https://user-images.githubusercontent.com/32676036/117693599-dfb8c000-b1c6-11eb-96a0-a4a1304ac76d.png)

http://berandomcloudcomputing.s3-website.eu-central-1.amazonaws.com/
## Warning! This is an amusement school project. I don't own the jokes or the gifs displayed (not even the background image). 
## Problem & description:
When I started to search for APIs to integrate in this project I had a bad day and I found the random joke API. I found the jokes funny and worth of sharing so I started thinking of a project that does random entertainment stuff. After a small research I found out that GIPHY has APIs and a specific random GIF API. When I need something dumb to amuse me, I enter on this AWS hosted website and I stay like 3 minutes rerolling jokes and GIFs. Have fun!
This website displays a random GIF and a random joke that can be rerolled. The GIF in embeded in an Iframe and breaks the SPA paradigm. The website it is based on web components and created with VueJS 2 and Bootstrap Vue. If you want to start this project locally you need to have NODE.js installed and NPM. It starts with npm run serve.

## APIs
### Random joke API - it is at free of use and it is provided by official-joke-api.appspot.com. They have 3 GET APIs "Try /random_joke, /random_ten, /jokes/random, or /jokes/ten" . I used the /random_joke. It does not require input parameters or query parameters. 
![image](https://user-images.githubusercontent.com/32676036/117805989-5d7dd980-b262-11eb-8331-00fe3778a4d5.png) 
#### The usage of the API- I take the setup and the punchline and display them when the user clicks on the corresponding buttons
### GIPHY random GIF API - it is a free of user API but with API-Key authorization – you need to sign up to GIPHY in order to get the API-key. They have multiple APIs, but the random GIF one suited my case.  Documentation of the APIs available from GIPHY -> https://developers.giphy.com/docs/api.
#### I used the api.giphy.com/v1/gifs/random that supports 4 request parameters ( just the API-key it is required, the others are optional) 
![image](https://user-images.githubusercontent.com/32676036/117808511-a2efd600-b265-11eb-9b50-34eca3c45b87.png)
#### In my project I used fetch for boths APIs - > 
![image](https://user-images.githubusercontent.com/32676036/117808959-36c1a200-b266-11eb-8820-c72202a5cfbe.png)
![image](https://user-images.githubusercontent.com/32676036/117809194-8d2ee080-b266-11eb-9e8a-ea464ce0515a.png)
```{
    "data": {
        "type": "gif",
        "id": "3ov9jEJO7MyAMk2feM",
        "url": "https://giphy.com/gifs/nbc-agt-americas-got-talent-3ov9jEJO7MyAMk2feM",
        "slug": "nbc-agt-americas-got-talent-3ov9jEJO7MyAMk2feM",
        "bitly_gif_url": "http://gph.is/2ffRds7",
        "bitly_url": "http://gph.is/2ffRds7",
        "embed_url": "https://giphy.com/embed/3ov9jEJO7MyAMk2feM",
        "username": "",
        "source": "http://www.nbc.com/americas-got-talent",
        "title": "americas got talent nbc GIF",
        "rating": "g",
        "content_url": "",
        "source_tld": "www.nbc.com",
        "source_post_url": "http://www.nbc.com/americas-got-talent",
        "is_sticker": 0,
        "import_datetime": "2017-09-13 01:56:17",
        "trending_datetime": "0000-00-00 00:00:00",
        "images": {
            "downsized_large": {
                "height": "262",
                "size": "3584530",
                "url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/giphy.gif?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=giphy.gif&ct=g",
                "width": "470"
            },
            "fixed_height_small_still": {
                "height": "100",
                "size": "12253",
                "url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/100_s.gif?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=100_s.gif&ct=g",
                "width": "180"
            },
            "original": {
                "frames": "62",
                "hash": "85dfbdc064d4cf46a35823c360b960b5",
                "height": "262",
                "mp4": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/giphy.mp4?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=giphy.mp4&ct=g",
                "mp4_size": "339824",
                "size": "3584530",
                "url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/giphy.gif?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=giphy.gif&ct=g",
                "webp": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/giphy.webp?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=giphy.webp&ct=g",
                "webp_size": "694172",
                "width": "470"
            },
            "fixed_height_downsampled": {
                "height": "200",
                "size": "247671",
                "url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/200_d.gif?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=200_d.gif&ct=g",
                "webp": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/200_d.webp?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=200_d.webp&ct=g",
                "webp_size": "41274",
                "width": "359"
            },
            "downsized_still": {
                "height": "139",
                "size": "22445",
                "url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/giphy-downsized_s.gif?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=giphy-downsized_s.gif&ct=g",
                "width": "250"
            },
            "fixed_height_still": {
                "height": "200",
                "size": "40204",
                "url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/200_s.gif?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=200_s.gif&ct=g",
                "width": "359"
            },
            "downsized_medium": {
                "height": "262",
                "size": "3584530",
                "url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/giphy.gif?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=giphy.gif&ct=g",
                "width": "470"
            },
            "downsized": {
                "height": "139",
                "size": "987538",
                "url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/giphy-downsized.gif?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=giphy-downsized.gif&ct=g",
                "width": "250"
            },
            "preview_webp": {
                "height": "163",
                "size": "49436",
                "url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/giphy-preview.webp?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=giphy-preview.webp&ct=g",
                "width": "292"
            },
            "original_mp4": {
                "height": "266",
                "mp4": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/giphy.mp4?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=giphy.mp4&ct=g",
                "mp4_size": "339824",
                "width": "480"
            },
            "fixed_height_small": {
                "height": "100",
                "mp4": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/100.mp4?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=100.mp4&ct=g",
                "mp4_size": "76758",
                "size": "565241",
                "url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/100.gif?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=100.gif&ct=g",
                "webp": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/100.webp?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=100.webp&ct=g",
                "webp_size": "165742",
                "width": "180"
            },
            "fixed_height": {
                "height": "200",
                "mp4": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/200.mp4?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=200.mp4&ct=g",
                "mp4_size": "202651",
                "size": "2082892",
                "url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/200.gif?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=200.gif&ct=g",
                "webp": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/200.webp?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=200.webp&ct=g",
                "webp_size": "414074",
                "width": "359"
            },
            "downsized_small": {
                "height": "176",
                "mp4": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/giphy-downsized-small.mp4?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=giphy-downsized-small.mp4&ct=g",
                "mp4_size": "101122",
                "width": "315"
            },
            "preview": {
                "height": "170",
                "mp4": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/giphy-preview.mp4?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=giphy-preview.mp4&ct=g",
                "mp4_size": "32039",
                "width": "304"
            },
            "fixed_width_downsampled": {
                "height": "111",
                "size": "83896",
                "url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/200w_d.gif?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=200w_d.gif&ct=g",
                "webp": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/200w_d.webp?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=200w_d.webp&ct=g",
                "webp_size": "18428",
                "width": "200"
            },
            "fixed_width_small_still": {
                "height": "56",
                "size": "5070",
                "url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/100w_s.gif?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=100w_s.gif&ct=g",
                "width": "100"
            },
            "fixed_width_small": {
                "height": "56",
                "mp4": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/100w.mp4?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=100w.mp4&ct=g",
                "mp4_size": "32847",
                "size": "194836",
                "url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/100w.gif?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=100w.gif&ct=g",
                "webp": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/100w.webp?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=100w.webp&ct=g",
                "webp_size": "75902",
                "width": "100"
            },
            "original_still": {
                "height": "262",
                "size": "64426",
                "url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/giphy_s.gif?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=giphy_s.gif&ct=g",
                "width": "470"
            },
            "fixed_width_still": {
                "height": "111",
                "size": "14092",
                "url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/200w_s.gif?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=200w_s.gif&ct=g",
                "width": "200"
            },
            "looping": {
                "mp4": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/giphy-loop.mp4?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=giphy-loop.mp4&ct=g",
                "mp4_size": "1841381"
            },
            "fixed_width": {
                "height": "111",
                "mp4": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/200w.mp4?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=200w.mp4&ct=g",
                "mp4_size": "84775",
                "size": "662844",
                "url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/200w.gif?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=200w.gif&ct=g",
                "webp": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/200w.webp?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=200w.webp&ct=g",
                "webp_size": "187086",
                "width": "200"
            },
            "preview_gif": {
                "height": "73",
                "size": "47916",
                "url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/giphy-preview.gif?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=giphy-preview.gif&ct=g",
                "width": "131"
            },
            "480w_still": {
                "url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/480w_s.jpg?cid=017c7fd45ddc7b2950fdff8288e0fcbe348b0dabb627dbe5&rid=480w_s.jpg&ct=g",
                "width": "480",
                "height": "268"
            }
        },
        "image_original_url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/giphy.gif",
        "image_url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/giphy.gif",
        "image_mp4_url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/giphy.mp4",
        "image_frames": "62",
        "image_width": "470",
        "image_height": "262",
        "fixed_height_downsampled_url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/200_d.gif",
        "fixed_height_downsampled_width": "359",
        "fixed_height_downsampled_height": "200",
        "fixed_width_downsampled_url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/200w_d.gif",
        "fixed_width_downsampled_width": "200",
        "fixed_width_downsampled_height": "111",
        "fixed_height_small_url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/100.gif",
        "fixed_height_small_still_url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/100_s.gif",
        "fixed_height_small_width": "180",
        "fixed_height_small_height": "100",
        "fixed_width_small_url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/100w.gif",
        "fixed_width_small_still_url": "https://media4.giphy.com/media/3ov9jEJO7MyAMk2feM/100w_s.gif",
        "fixed_width_small_width": "100",
        "fixed_width_small_height": "56",
        "caption": ""
    },
    "meta": {
        "status": 200,
        "msg": "OK",
        "response_id": "5ddc7b2950fdff8288e0fcbe348b0dabb627dbe5"
    }
}
```

#### The usage of API- I take the "embed_url" and pass it to an IFrame src that loads the embeds the GIPHY GIF.
#### For both APIs fetch was used - see the picture below
![image](https://user-images.githubusercontent.com/32676036/117809036-51941680-b266-11eb-9015-4dfa426bc8c3.png)





###### Owner of this VueJS project but not of the APIs or of the images - Adrian Neagoe
###### background image - https://wallpaperaccess.com/download/joker-cartoon-82901
###### joke api - https://official-joke-api.appspot.com/random_joke
###### gif api - https://api.giphy.com/v1/gifs/random?

###### aws link - http://berandomcloudcomputing.s3-website.eu-central-1.amazonaws.com/

