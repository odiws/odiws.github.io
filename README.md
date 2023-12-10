<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
<meta name="viewport"
      content="width=device-width, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
<meta http-equiv="X-UA-Compatible" content="ie=edge">

    <meta name="author" content="John Doe">





<title>Hexo</title>



    <link rel="icon" href="/favicon.ico">




    <!-- stylesheets list from _config.yml -->
    
    <link rel="stylesheet" href="/css/style.css">
    



    <!-- scripts list from _config.yml -->
    
    <script src="/js/script.js"></script>
    
    <script src="/js/tocbot.min.js"></script>
    



    
    
        
    


<meta name="generator" content="Hexo 7.0.0"></head>

<body>
    <script>
        // this function is used to check current theme before page loaded.
        (() => {
            const currentTheme = window.localStorage && window.localStorage.getItem('theme') || '';
            const isDark = currentTheme === 'dark';
            const pagebody = document.getElementsByTagName('body')[0]
            if (isDark) {
                pagebody.classList.add('dark-theme');
                // mobile
                document.getElementById("mobile-toggle-theme").innerText = "· Dark"
            } else {
                pagebody.classList.remove('dark-theme');
                // mobile
                document.getElementById("mobile-toggle-theme").innerText = "· Light"
            }
        })();
    </script>

    <div class="wrapper">
        <header>
    <nav class="navbar">
        <div class="container">
            <div class="navbar-header header-logo"><a href="/">Bentham&#39;s Blog</a></div>
            <div class="menu navbar-right">
                
                    <a class="menu-item" href="/archives">Posts</a>
                
                    <a class="menu-item" href="/category">Categories</a>
                
                    <a class="menu-item" href="/tag">Tags</a>
                
                    <a class="menu-item" href="/about">About</a>
                
                <input id="switch_default" type="checkbox" class="switch_default">
                <label for="switch_default" class="toggleBtn"></label>
            </div>
        </div>
    </nav>

    
    <nav class="navbar-mobile" id="nav-mobile">
        <div class="container">
            <div class="navbar-header">
                <div>
                    <a href="/">Bentham&#39;s Blog</a><a id="mobile-toggle-theme">·&nbsp;Light</a>
                </div>
                <div class="menu-toggle" onclick="mobileBtn()">&#9776; Menu</div>
            </div>
            <div class="menu" id="mobile-menu">
                
                    <a class="menu-item" href="/archives">Posts</a>
                
                    <a class="menu-item" href="/category">Categories</a>
                
                    <a class="menu-item" href="/tag">Tags</a>
                
                    <a class="menu-item" href="/about">About</a>
                
            </div>
        </div>
    </nav>

</header>
<script>
    var mobileBtn = function f() {
        var toggleMenu = document.getElementsByClassName("menu-toggle")[0];
        var mobileMenu = document.getElementById("mobile-menu");
        if(toggleMenu.classList.contains("active")){
           toggleMenu.classList.remove("active")
            mobileMenu.classList.remove("active")
        }else{
            toggleMenu.classList.add("active")
            mobileMenu.classList.add("active")
        }
    }
</script>
            <div class="main">
                
    <div class="container profile-container">
    <div class="intro">
        <div class="avatar">
            <a href="/archives"><img src="/image/asdfg.jpg"></a>
        </div>
        <div class="nickname">odiws</div>
        <div class="description"><p>Lorem ipsum dolor sit amet, <strong>consectetur adipiscing elit.</strong> <br>Fusce eget urna vitae velit <em>eleifend interdum at ac</em> nisi.</p>
</div>
        <div class="links">
            
                
                    <a class="link-item" title="Blog" href="/archives">
                        
                        
                            <i class="iconfont icon-blog"></i>
                        
                    </a>
                
                    <a class="link-item" title="ZhiHu" target="_blank" rel="noopener" href="https://www.zhihu.com/people/sirice">
                        
                        
                            <i class="iconfont icon-zhihu"></i>
                        
                    </a>
                
                    <a class="link-item" title="Instagram" href="">
                        
                        
                            <i class="iconfont icon-instagram"></i>
                        
                    </a>
                
                    <a class="link-item" title="Reddit" href="">
                        
                        
                            <i class="iconfont icon-reddit"></i>
                        
                    </a>
                
                    <a class="link-item" title="Github" target="_blank" rel="noopener" href="https://github.com/Siricee">
                        
                        
                            <i class="iconfont icon-github"></i>
                        
                    </a>
                
            
        </div>
    </div>
</div>


    <!-- ѩ����Ч -->
<script type="text/javascript" src="https://libs.baidu.com/jquery/1.8.3/jquery.js">
</script>
<script type="text/javascript"
src="https://libs.baidu.com/jquery/1.8.3/jquery.min.js"></script>

<script type="text/javascript" src="/js/snow.js"></script>
            </div>
            <footer id="footer" class="footer">
    <div class="copyright">
        <span>© John Doe | Powered by <a href="https://hexo.io" target="_blank">Hexo</a> & <a href="https://github.com/Siricee/hexo-theme-Chic" target="_blank">Chic</a></span>
    </div>
</footer>

    </div>
</body>

</html>
