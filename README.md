# hk
Link shorter 
import urllib.parse
import urllib.request


def shorten_url(long_url):
  api_url = (
      "http://tinyurl.com/api-create.php?url="
      + urllib.parse.quote(long_url)
  )
  try:
    with urllib.request.urlopen(api_url) as response:
      return response.read().decode("utf-8")
  except Exception as e:
    return f"Error: {e}"


# Example usage:
long_link = "https://www.example.com/very/long/path/to/your/page"
print("Shortened URL:", shorten_url(long_link))
