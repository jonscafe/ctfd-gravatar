# ctfd-gravatar
copy the init.py on the repo into your own CTFd source code.


ctfd > themes > themefolder > templates > scoreboard.html
ctfd > themes > themefolder > templates > users.html
ctfd > themes > themefolder > templates > public.html
ctfd > themes > themefolder > templates > private.html
ctfd > themes > themefolder > templates > settings.html

add these codes into that files
---------------------------------- for scoreboard, using standings
<img
width="50"
height="50"
loading="lazy"
class="cellBodyIcon"
src="{{ standing.gravatar }}"
data-fallback="https://api.dicebear.com/7.x/initials/svg?seed={{ standing.name }}"
onerror="this.src = this.dataset.fallback;this.onerror='';"
style="border: 2px solid #7E57C2; border-radius: 50%;"
>


---------------------------------- for profile/users, using user
<img
width="50"
height="50"
loading="lazy"
class="cellBodyIcon"
src="{{ user.gravatar('404') }}"
data-fallback="https://api.dicebear.com/7.x/initials/svg?seed={{ user.name }}"
onerror="this.src = this.dataset.fallback;this.onerror='';"
style="border: 2px solid #7E57C2; border-radius: 50%;"
>


--------------------------------------------------------------------
adjust it how did you need it.

it will call gravatar API to gravatar profile using hashed email address from your registered users. If it didnt found the gravatar profile, it will call dicebear api to generate random avatar.
