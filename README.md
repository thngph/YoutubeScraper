# YoutubeScraper
© Ngô Phước Thịnh - 19520981

YoutubeScraper is a custom class based on [pytube](https://pytube.io/en/latest/).



YoutubeScraper(search_list, maxResult):

Default parameters:

search_list: list, default None list of keyword used to search.

maxResult: int, default 50 - Note that this number is just an approximate since each time pytube Search module returns 17 results. Besides that, to prevent some error from pytube, so high maxResult value is not recommend (should be around 300 max).

YoutubeScraper.get_id(): return ID list (YoutubeCraper._id_list) based on keywords (Youtubescraper.search_list), using pytube Search module.
YoutubeScraper.get_info(): using self._id_list, the method returns title, description and keywords of each video having the ID (YotubeScraper._title_list, YoutubeScraper._keywords_list, YoutubeScraper._description_list).
Ví dụ:
```
> yt = YoutubeScraper(["music", "trending"], 50)
> yt.get_id()
> yt.list_id
    ...
> yt.get_info()
> yt.list_title
    ...
```    
    
Note: data scraping will send tons of request to pytube and Youtube sever. To prevent server block, I have set a litle sleep() after each time request are sent. You can eliminate this step if the maxResult is not so huge (under 100).
