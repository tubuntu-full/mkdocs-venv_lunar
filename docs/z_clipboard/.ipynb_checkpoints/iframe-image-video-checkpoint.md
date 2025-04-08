# 1.0 iframes

**Embed an internal page within a website**

---

<iframe src="https://ocrobotix.github.io/lunarlander/hidden_page/" width="100%" height="300px" style="border:none;">
  Your browser does not support iframes.
</iframe>



---



**Embed page from an external website (NASA)**

<iframe src="https://www.nasa.gov/news-release/nasa-provides-update-on-artemis-iii-moon-landing-regions/" width="100%" height="600px" style="border:none;">
  Your browser does not support iframes.
</iframe>

# 2.0 Images

**Method 1**

![Test clip](../img/test.png)
*Image Caption*

`<br><br>`

**Method 2**

![nasa](../img/artemis-iii-landing-region-candidates.webp)      Image Image Caption 2

`<br><br>`

**Method 3**

<figure>
    <a href="https://www.nasa.gov/news-release/nasa-provides-update-on-artemis-iii-moon-landing-regions/">
        <img src="../img/artemis-iii-landing-region-candidates.webp" width="300"  alt="My image">
    </a>
    <figcaption>This is my caption</figcaption>
</figure>

`<br><br>`

# 3.0 Videos

**Apollo Lunar Module descent simulation**

<video
    width="640"
    height="360"
    controls
    preload="none"
    poster="../video/lunar2.png"
    class="video-container"
    playsinline
    controlsList="nodownload">
    <source src="../video/lunar.mp4" type="video/mp4">
    <!-- <source src="../video/lunar2.mkv" type="video/x-matroska"> -->
    <p>Your browser does not support HTML5 video. Please use a modern browser.</p>
</video>

<!-- To The Top -->
