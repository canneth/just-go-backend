<header align='center'>
  <h1>
    <div display='flex' align-items='center'>
      JustGo!
      <img src='https://user-images.githubusercontent.com/23531034/148372740-681d6810-c6ef-4560-b64e-996db9079e1e.png#gh-light-mode-only' />
      <img src='https://user-images.githubusercontent.com/23531034/148373133-da36d27f-8f04-49f4-a7c1-ecefd5818801.png#gh-dark-mode-only' />
    </div>
  </h1>
</header>

<p align='center'>
  Feel the sudden urge to be out and about, but just can't think of the place to go?
  <br />
  This humble app helps you decide on that special somewhere!
</p>

<h2>Foreword</h2>
This is my first crack at developing an entire web app, and this entire project is primarily a learning exercise in implementing a proper backend. This repo contains only the backend of this web app. To view the corresponding frontend repo, <a href='https://github.com/canneth/just-go-frontend' rel='noreferrer'>click here</a>.

<h2>Development status</h2>
I have yet to begin work on this backend, so at the moment, you may consider it <strong>completely absent</strong>.
<br />
However, I have a rough idea on the endpoints that I will need to implement in this backend, and I shall use this README.md to present and organise my ideas as I proceed with development.
As this will be a living document, expect there to be frequent changes.

<h3>API endpoints</h3>
<section>
  <h4>GET: <code>/search?q=[rawSearchInput]</code></h4>
  <h5>When this is called</h5>
  <p>
    On the <a href='https://justgo.dev/search' rel='noreferrer'>search page</a>, when the user submits a search.
  </p>
  <h5>Parameters</h5>
  <p>
    <code>rawSearchInput</code> - The raw input, as entered and submitted.
  </p>
  <h5 class='extended-markdown tip border rounded-1 mb-4 p-3 color-border-accent-emphasis color-bg-accent f5'>What should happen before the response is returned</h5>
  <p>
    <ol>
      Sanitise and format <code>rawSearchInput</code> for use in the API call to the place API.
      Call the place API and receive a list of matching places as <code>rawPlaceList</code>.
      If the user is logged in, check the user's favourites to see if any of the places are favourites and mark them accordingly, storing the marked list as <code>augmentedPlaceList</code>.
      Return <code>augmentedPlaceList</code> as the response.
    </ol>
  </p>
  
</section>
