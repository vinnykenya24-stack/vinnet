<article class="post" data-id="1">
    <h3>Crafting Shareable Content</h3>
    <p>Tips to create posts that resonate and get shared.</p>
    <div class="share" aria-label="Share this article">
      <button class="btn" onclick="shareNow('Crafting Shareable Content')">Share</button>
    </div>
  </article>

  <article class="post" data-id="2">
    <h3>Engagement That Builds Community</h3>
    <p>Strategies to foster genuine conversations with your audience.</p>
    <div class="share" aria-label="Share this article">
      <button class="btn" onclick="shareNow('Engagement That Builds Community')">Share</button>
    </div>
  </article>
</section>

<!-- Newsletter Signup -->
<section class="card" id="signup">
  <h2>Join Our Newsletter</h2>
  <p>Get weekly tips on ethical growth and audience engagement.</p>
  <form id="signupForm" onsubmit="handleSignup(event)">
    <input id="email" type="email" placeholder="Your email" required style="padding:.5rem; width:60%; min-width:250px;" />
    <button class="btn" type="submit" style="margin-left:.5rem;">Join</button>
  </form>
  <p id="signupMsg" style="color:#2a7f62; display:none;">Thanks for joining! Check your inbox.</p>
</section>
