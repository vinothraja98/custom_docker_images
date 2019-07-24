<article class="markdown-body entry-content p-5" itemprop="text"><h1><a id="user-content-selenium-docker" class="anchor" aria-hidden="true" href="#selenium-docker"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>Custom Selenium Chrome Debug Docker with root user access </h1>
<p>The project is made with multiple image codes combined into a single **Dockerfile**.</p>
<p>Image included:</p>
<ul>
<li><strong>selenium/standalone-chrome-debug</strong>: Selenium Standalone with Chrome installed.</li>
<li><strong>Vnc</strong>: Runs a VNC server.</li>
<li><strong>Python 3.7</strong>: Python 3.7 pre-built.</li>
<li><strong>User seluser (Root)</strong>: seluser username with sudo access and as root.</li>
</ul>

<p>Installation : <br>
Download all the file to your local <br>
Move into the downloaded folder where the Dockerfile is present. <br></p>
<p><g-emoji class="g-emoji" alias="exclamation" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/2757.png">💻❗️</g-emoji> To build the image from the Dockefile, execute <code>docker build</code> as follows.</p>
<p><g-emoji class="g-emoji" alias="exclamation" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/2757.png">💻❗️</g-emoji> <code>Run : docker build -t **{nameofyourImage}** .</code>.</p>

  
<p><g-emoji class="g-emoji" alias="exclamation" fallback-src="https://github.githubassets.com/images/icons/emoji/unicode/2757.png">🏁</g-emoji> When executing <code>docker run</code> for an image with Chrome please either mount <code>-v /dev/shm:/dev/shm</code> or use the flag <code>--shm-size=2g</code> to use the host's shared memory.</p>
<p>Chrome</p>
<div class="highlight highlight-source-shell"><pre>$ docker run -d -p 4444:4444 -v /dev/shm:/dev/shm **Image-name**
<span class="pl-c"><span class="pl-c">#</span>OR</span>
$ docker run -d --name **nameofcontainer** -p 4441:4444 -p 5901:5900 **ImageID** </pre></div>
