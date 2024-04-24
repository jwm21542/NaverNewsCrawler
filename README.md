# NaverNewsCrawler
### Crawler for Naver News:

This crawler will grab all articles related to keywords of your choosing. It will also grab all comments and date of the comments in those articles grabbed as well.

Naver website does not have a search function for articles within their news section directly. They do only via their general search engine and then you have to view articles on the original publisher's website. This does not allow you to view Naver comments on the articles, as you can in the News section. This crawler will go to the specific news section of your choosing and grab articles based on the keywords you selected. Another lacking function of Naver is that you cannot view all articles, only within a certain amount of time, usually around ~6 days. Naver news is poorly structured and lacks a lot of search and filter functionality. This crawler will at least grab all that is possible to grab from Naver news.

The news sections are on the top header:
![Screenshot_20240424_105129](https://github.com/jwm21542/NaverNewsCrawler/assets/108346833/33b26e54-9823-4be8-9562-7847e9d4f65b)

### Required Libaries:
- selenium

```
pip install -U selenium
```

### Variables you may want to change:
```
KEYWORD_LIST = ['의료', '의대']
#url =  'https://news.naver.com/main/main.naver?mode=LSD&mid=shm&sid1=101' #경제
#url = 'https://news.naver.com/main/main.naver?mode=LSD&mid=shm&sid1=100' #정치
url = 'https://news.naver.com/main/main.naver?mode=LSD&mid=shm&sid1=102' #사회
```

The KEYWORD_LIST is just simply a list of keywords you want to set. If an article title contains any of these keywords, it will add them to the list of articles.

The URL is the URL of the particular news section you want to view. You will need to grab the URL for any of the sections in the above image. I have put economics, politics, and society URLs as these are the main sections.

Naver website configuration changes very frequently. This current iteration is the second form. If the crawler needs to be updated to match Naver's updates, please comment and let me know and I will update accordingly.

### Using ChromeDriver: 
Make sure you have downloaded the latest ChromeDriver file, which you can find [here](https://chromedriver.chromium.org/getting-started), make sure to get the correct one for your OS and Chrome version. It may be necessary to update your Chrome as well.

```
driver = webdriver.Chrome(options=options, executable_path=ChromeDriverManager().install())
```

This is to create a driver instance in **Linux**. You will have to change this line if your OS is NOT linux. 

For example, this would be what you would change it to in **Windows**:
```
# Specify the path to the ChromeDriver executable if not added to PATH
chrome_driver_path = 'path/to/chromedriver.exe'

# Create ChromeDriver instance
driver = webdriver.Chrome(executable_path=chrome_driver_path)
```
Initializing ChromeDriver is simple but may differ by your environment, so please correctly configure if my current setting does not work on your os.

# NaverNewsCrawler
### 네이버 뉴스 크롤러:

이 크롤러는 선택한 키워드와 관련된 모든 기사를 수집합니다. 또한 해당 기사에서 수집된 모든 댓글과 댓글의 날짜를 가져옵니다.

네이버 웹사이트에는 뉴스 섹션 내의 기사에 대한 검색 기능이 직접적으로 제공되지 않습니다. 일반 검색 엔진을 통해서만 가능하며, 그런 다음 원래 게시자 웹사이트에서 기사를 볼 수 있습니다. 이로 인해 뉴스 섹션의 네이버 댓글을 기사에서 볼 수 없습니다. 이 크롤러는 선택한 키워드를 기반으로 원하는 특정 뉴스 섹션으로 이동하여 기사를 수집합니다. 또한 네이버의 부족한 기능 중 하나는 모든 기사를 볼 수 없으며, 보통 약 6일 정도의 기간 내에서만 가능합니다. 네이버 뉴스는 검색 및 필터링 기능이 많이 부족합니다. 이 크롤러는 최소한 네이버 뉴스로부터 수집할 수 있는 모든 것을 수집합니다.

뉴스 섹션은 상단 헤더에 있습니다:
![Screenshot_20240424_105129](https://github.com/jwm21542/NaverNewsCrawler/assets/108346833/33b26e54-9823-4be8-9562-7847e9d4f65b)

### 필요한 라이브러리:
- selenium

```
pip install -U selenium
```

### 변경 필요한 변수:
```
KEYWORD_LIST = ['의료', '의대']
#url =  'https://news.naver.com/main/main.naver?mode=LSD&mid=shm&sid1=101' #경제
#url = 'https://news.naver.com/main/main.naver?mode=LSD&mid=shm&sid1=100' #정치
url = 'https://news.naver.com/main/main.naver?mode=LSD&mid=shm&sid1=102' #사회
```


KEYWORD_LIST는 단순히 설정하려는 키워드 목록입니다. 기사 제목에 이 키워드 중 하나가 포함되면 해당 기사를 기사 목록에 추가합니다.

URL은 보고 싶은 특정 뉴스 섹션의 URL입니다. 위 이미지에 나와 있는 섹션 중 하나의 URL을 가져와야 합니다. 주요 섹션으로 경제, 정치, 사회 URL을 넣었습니다.

네이버 웹사이트 구성이 자주 변경됩니다. 현재 버전은 두 번째 형태입니다. 크롤러를 네이버의 업데이트와 일치시키려면 댓글을 남겨 알려주시면 해당 부분을 업데이트하겠습니다.


### ChromeDriver 사용전: 
최신 ChromeDriver 파일을 다운로드했는지 확인하세요. 여기에서 찾을 수 있습니다. 사용 중인 OS 및 Chrome 버전에 맞는 것을 가져오세요. Chrome을 업데이트해야 할 수도 있습니다.

리눅스로 드라이버 인스턴스 만들기: 
```
driver = webdriver.Chrome(options=options, executable_path=ChromeDriverManager().install())
```

이것은 **리눅스**에서 드라이버 인스턴스를 만드는 것입니다. 사용 중인 OS가 리눅스가 아닌 경우 이 줄을 변경해야 합니다.

예를 들어, **윈도우**에서는 다음과 같이 변경해야 합니다:
```
# Specify the path to the ChromeDriver executable if not added to PATH
chrome_driver_path = 'path/to/chromedriver.exe'

# Create ChromeDriver instance
driver = webdriver.Chrome(executable_path=chrome_driver_path)
```

ChromeDriver를 초기화하는 것은 간단하지만 환경에 따라 다를 수 있으므로, 현재 설정이 작동하지 않는 경우 환경에 맞게 수정하세요.

