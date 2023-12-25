# ctfd-gravatar
<p>copy the init.py on the repo into your own CTFd source code.


<p>ctfd > themes > themefolder > templates > scoreboard.html
<p>ctfd > themes > themefolder > templates > users.html
<p>ctfd > themes > themefolder > templates > public.html
<p>ctfd > themes > themefolder > templates > private.html
<p>ctfd > themes > themefolder > templates > settings.html
<p>
<p>add these codes into that files
<p>---------------------------------- for scoreboard, using standings
<code>
&lt;img
width="50"
height="50"
loading="lazy"
class="cellBodyIcon"
src="{{ standing.gravatar }}"
data-fallback="https://api.dicebear.com/7.x/initials/svg?seed={{ standing.name }}"
onerror="this.src = this.dataset.fallback;this.onerror='';"
style="border: 2px solid #7E57C2; border-radius: 50%;"
&gt;
</code>

<p>---------------------------------- for profile/users, using user
<code>
&lt;img
width="50"
height="50"
loading="lazy"
class="cellBodyIcon"
src="{{ user.gravatar('404') }}"
data-fallback="https://api.dicebear.com/7.x/initials/svg?seed={{ user.name }}"
onerror="this.src = this.dataset.fallback;this.onerror='';"
style="border: 2px solid #7E57C2; border-radius: 50%;"
&gt;
</code>

<p>--------------------------------------------------------------------
<p>adjust it how did you need it.
<p>
<p>it will call gravatar API to gravatar profile using hashed email address from your registered users. If it didnt found the gravatar profile, it will call dicebear api to generate random avatar.
