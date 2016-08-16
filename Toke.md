After spending a lot of time on the website and not finding anything interesting I noticed 2 extra cookies, jwt_token and session. <br>
Reading about jwt tokens on wikipedia I found out that they are base64 encoded. (https://en.wikipedia.org/wiki/JSON_Web_Token)<br>

Intially I thought I'll have to change the user value to admin or something but, simply decoding the cookie gave away the flag.<br>
<b>IceCTF{jW7_t0K3ns_4Re_nO_p14CE_fOR_53CrE7S}</b>
