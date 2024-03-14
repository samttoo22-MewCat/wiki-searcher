以下是轉換為 Markdown 語法的自述文件：

# Wikipedia Scraper

這是一個 Python 腳本，用於在 Wikipedia 上進行關鍵字搜索，獲取搜索結果的連結，並從這些連結中抓取段落文本內容。

## 使用方式

1. 確保您已安裝了以下 Python 庫：
   - `seleniumbase`
   - `selenium`
   - `requests`
   - `beautifulsoup4`
2. 創建一個 `WikiSearcher` 類的實例，然後調用 `get_search_results` 方法獲取與關鍵字匹配的 Wikipedia 連結。
3. 使用 `scrap` 方法抓取每個連結的內容。

## 功能

- `WikiSearcher` 類:
  - 初始化瀏覽器驅動並訪問 Wikipedia 首頁。
  - `get_search_results` 方法接受關鍵字和結果數量作為參數，返回搜索結果連結列表。
  - `scrap` 方法接受一個 URL 作為參數，從該網頁中抓取純文本內容並打印出來。

## 注意事項

- 腳本使用 Selenium 啟動 Chrome 瀏覽器進行搜索和解析。
- 腳本會自動忽略 Wikipedia 中的特殊頁面、圖像文件和引文等內容。
- 腳本目前只打印抓取的純文本內容，您可以根據需要修改輸出方式。

## 示例用法

```python
wiki_searcher = WikiSearcher()
search_results = wiki_searcher.get_search_results('台中市', 2)
print(len(search_results))
for search_result in search_results:
    wiki_searcher.scrap(search_result)
```

上述代碼將在 Wikipedia 上搜索"台中市"，獲取前 2 個搜索結果的連結，然後抓取並打印這些頁面的純文本內容。

請注意，在實際使用時，您可能需要根據您的具體需求對腳本進行修改和優化。
