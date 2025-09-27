# Instagram
<!-- Instagram-style (safe demo) login UI for Blogger
     IMPORTANT: Demo only. This DOES NOT connect to Instagram or send credentials anywhere.
     Change data-site-name and visible text to your blog name before publishing.
-->
<div id="insta-style-root" data-site-name="MyBlogger" style="font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial; display:flex; justify-content:center; padding:40px 12px;">
  <style>
    /* Scoped styles so they don't affect other Blogger elements */
    #insta-style-root .wrapper { display:flex; gap:40px; align-items:center; max-width:930px; width:100%; }
    #insta-style-root .phone {
      width: 380px; height: 640px; background: linear-gradient(180deg,#fff 0%, #fafafa 100%);
      border-radius: 36px; box-shadow: 0 18px 40px rgba(18,18,18,0.12); position:relative;
      overflow:hidden; display:flex; flex-direction:column; justify-content:center; align-items:center;
    }
    #insta-style-root .phone .screen {
      width:88%; height:86%; background: url('https://images.unsplash.com/photo-1508921912186-1d1a45ebb3c1?q=80&w=1200&auto=format&fit=crop&ixlib=rb-4.0.3&s=placeholder') center/cover no-repeat; border-radius:20px; box-shadow: inset 0 0 0 8px rgba(255,255,255,0.35);
      display:flex; align-items:flex-end; justify-content:center; padding:18px; box-sizing:border-box;
      color:white; font-weight:700; text-shadow: 0 1px 3px rgba(0,0,0,0.45);
    }

    /* Right column: form box */
    #insta-style-root .box {
      width:360px; background: white; border-radius:10px; box-shadow: 0 8px 22px rgba(16,16,16,0.08);
      padding:20px 28px; box-sizing:border-box;
    }
    #insta-style-root .brand {
      text-align:center; margin-bottom:14px;
    }
    #insta-style-root .brand h1 {
      margin:0; font-size:28px; letter-spacing:1px; color:#111;
    }
    #insta-style-root .brand p { margin:6px 0 0; color:#666; font-size:13px; }

    /* form inputs */
    #insta-style-root .form input[type="text"],
    #insta-style-root .form input[type="password"] {
      width:100%; padding:10px 12px; margin:8px 0; border:1px solid #e9e9e9; border-radius:6px; font-size:14px; box-sizing:border-box;
      background:#fff;
    }
    #insta-style-root .form button {
      width:100%; padding:10px; margin-top:8px; border-radius:6px; border:none; cursor:pointer;
      background: linear-gradient(90deg,#6a11cb 0%, #2575fc 100%); color:white; font-weight:700; font-size:15px;
      box-shadow: 0 6px 14px rgba(37,117,252,0.18);
    }
    #insta-style-root .links { display:flex; justify-content:space-between; align-items:center; margin-top:10px; font-size:13px; color:#7b7b7b; }
    #insta-style-root .links a { color:#2575fc; text-decoration:none; font-weight:600; }

    /* Divider and sign-up */
    #insta-style-root .divider { display:flex; align-items:center; gap:12px; margin:16px 0; color:#9b9b9b; font-size:13px; }
    #insta-style-root .divider .line { flex:1; height:1px; background:#efefef; }
    #insta-style-root .signup { text-align:center; padding:12px 10px; border-radius:8px; background:#fbfbfd; color:#333; font-size:14px; }

    /* small note */
    #insta-style-root .note { text-align:center; margin-top:10px; color:#9a9a9a; font-size:12px; }
    /* responsive */
    @media (max-width:880px) {
      #insta-style-root .wrapper { flex-direction:column; gap:18px; align-items:center; }
      #insta-style-root .phone { width:320px; height:540px; }
    }
  </style>

  <div class="wrapper">
    <!-- phone mockup (decorative) -->
    <div class="phone" aria-hidden="true">
      <div class="screen">
        <!-- decorative title -->
        <div style="text-align:center;">
          <div style="font-size:16px; opacity:0.95;">Share your moments</div>
          <div style="font-size:12px; opacity:0.9; margin-top:6px;">A demo preview for your blog</div>
        </div>
      </div>
    </div>

    <!-- form box -->
    <div class="box" role="region" aria-labelledby="login-title">
      <div class="brand">
        <h1 id="login-title">Insta‑style Sign In</h1>
        <p>Sign in to <strong id="site-name-display">MyBlogger</strong> (demo only)</p>
      </div>

      <!-- FORM (demo only) -->
      <form id="instaDemoForm" class="form" autocomplete="off" novalidate>
        <input id="demo-user" type="text" placeholder="Phone number, username or email" aria-label="username or email" required>
        <input id="demo-pass" type="password" placeholder="Password" aria-label="password" required>
        <button type="submit" aria-label="Log in">Log In</button>

        <div class="links" style="margin-top:12px;">
          <label style="display:flex;align-items:center;gap:8px;font-size:13px;color:#6d6d6d;">
            <input id="remember" type="checkbox" style="width:14px;height:14px;">
            Remember
          </label>
          <a href="#" id="forgot-link">Forgot password?</a>
        </div>

        <div id="status" style="margin-top:12px;font-size:13px;min-height:20px;"></div>
      </form>

      <div class="divider" aria-hidden="true">
        <div class="line"></div>
        <div>OR</div>
        <div class="line"></div>
      </div>

      <div style="text-align:center;">
        <a href="#" id="social-login" style="display:inline-flex; gap:8px; align-items:center; color:#385185; font-weight:700; text-decoration:none;">
          <!-- simple svg to evoke social login (not a real Instagram icon) -->
          <svg width="18" height="18" viewBox="0 0 24 24" fill="none" aria-hidden="true" xmlns="http://www.w3.org/2000/svg"><path d="M12 12c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4z" stroke="#385185" stroke-width="1.4" stroke-linecap="round" stroke-linejoin="round"/><path d="M21 20v-2a4 4 0 0 0-4-4H7a4 4 0 0 0-4 4v2" stroke="#385185" stroke-width="1.4" stroke-linecap="round" stroke-linejoin="round"/></svg>
          Log in with Facebook
        </a>
      </div>

      <div class="signup" style="margin-top:14px;">
        Don’t have an account? <a href="#" id="create-link" style="color:#2575fc;text-decoration:none;font-weight:700;">Sign up</a>
      </div>

      <div class="note">
        <em>Demo UI only — this form does not submit credentials. Do not enter real passwords you use elsewhere.</em>
      </div>
    </div>
  </div>
</div>

<script>
/* Demo behavior only. Does NOT send data anywhere.
   Replace 'MyBlogger' with your blog name by editing the data-site-name attribute on #insta-style-root.
*/
(function(){
  const root = document.getElementById('insta-style-root');
  const siteName = root.getAttribute('data-site-name') || 'MyBlogger';
  document.getElementById('site-name-display').textContent = siteName;

  const form = document.getElementById('instaDemoForm');
  const status = document.getElementById('status');
  const forgot = document.getElementById('forgot-link');
  const create = document.getElementById('create-link');
  const social = document.getElementById('social-login');

  function setStatus(msg, isError) {
    status.textContent = msg;
    status.style.color = isError ? 'crimson' : '#2c7aef';
  }

  form.addEventListener('submit', function(e){
    e.preventDefault();
    const user = document.getElementById('demo-user').value.trim();
    const pass = document.getElementById('demo-pass').value;

    if (!user) { setStatus('Please enter username or email.', true); return; }
    if (pass.length < 6) { setStatus('Password must be at least 6 characters.', true); return; }

    setStatus('Signing in…');

    // Simulate success — do not send real credentials anywhere
    setTimeout(() => {
      setStatus(`Welcome back, ${sanitize(user)}! (demo — not connected to Instagram)`);
      // Example: redirect to a dashboard page on your blog (uncomment and change when ready)
      // window.location.href = '/dashboard.html';
    }, 700);
  });

  forgot.addEventListener('click', function(e){ e.preventDefault(); setStatus('Password reset link would be sent here (demo).', false); });
  create.addEventListener('click', function(e){ e.preventDefault(); setStatus('Sign-up flow would start here (demo).', false); });
  social.addEventListener('click', function(e){ e.preventDefault(); setStatus('Social login would open here (demo).', false); });

  function sanitize(s){
    const d = document.createElement('div');
    d.textContent = s;
    return d.innerHTML;
  }
})();
</script>
