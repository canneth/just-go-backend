<div align='center'>
  <h1>
    <div display='flex' align-items='center'>
      JustGo!
      <img src='https://user-images.githubusercontent.com/23531034/148372740-681d6810-c6ef-4560-b64e-996db9079e1e.png#gh-light-mode-only' />
      <img src='https://user-images.githubusercontent.com/23531034/148373133-da36d27f-8f04-49f4-a7c1-ecefd5818801.png#gh-dark-mode-only' />
    </div>
  </h1>
</div>

<p align='center'>
  Feel the sudden urge to be out and about, but just can't think of the place to go?
  <br />
  This humble app helps you decide on that special somewhere!
</p>

<br />

<h2>Foreword</h2>
This project serves primarily as a meaningful reason for me to get my hands dirty learning TypeScript, NestJS, PassportJS, Mongoose, and backend development in general. This repo contains only the backend of this web app. To view the corresponding frontend repo, <a href='https://github.com/canneth/just-go-frontend' rel='noreferrer'>click here</a>.

<h2>Development status</h2>
I have yet to begin work on this backend, so at the moment, you may consider it <strong>completely absent</strong>.
<br /><br />
As I plan out the endpoints I will be needing, I shall use this README.md to present and organise my ideas as I proceed with development. As this will be a living document, expect there to be frequent changes.

<h2>API endpoints</h2>

<details>
  
  <summary>
    <b>GET: <code>/search?q=[rawSearchInput]</code></b>
  </summary>
  
  <br />
  
  Returns a list of places, each with place details and corresponding hyperlocal weather data (current and 2hr forecast).
  
  <h4>Parameters</h4>
  <ul>
    <li><code>rawSearchInput</code> - The raw input, as entered and submitted.</li>
  </ul>
  
  <h4>What should happen before the response is returned</h4>
  <ol>
    <li>Sanitise and format <code>rawSearchInput</code> for use in the API call to the place API.</li>
    <li>Call the place API and receive a list of matching places as <code>rawPlaceList</code>.</li>
    <li>Call the weather API and receive weather data.</li>
    <li>Combine place list and the corresponding weather data into a new list <code>placeList</code>.</li>
    <li>If the user is logged in, check the user's favourites to see if any of the places are favourites and mark them accordingly in <code>placeListWithWeather</code>.</li>
    <li>Return <code>placeListWithWeather</code> as the response.</li>
  </ol>
  
  <hr />
  
</details>

<details>
  
  <summary>
    <b>GET: <code>/user/favourites</code></b>
  </summary>
  
  <br />
  
  Returns a list of places representing the favourites of the current user.
  
  <h4>Parameters</h4>
  <ul>
    <li><code>rawSearchInput</code> - The raw input, as entered and submitted.</li>
  </ul>
  
  <h4>What should happen before the response is returned</h4>
  <ol>
    <li>If there is a session token, deserialise user from session.</li>
    <li>Fetch a list of favourite places from from database, storing as <code>favouritesList</code>.</li>
    <li>Call the weather API and receive weather data.</li>
    <li>Combine place list and the corresponding weather data into a new list <code>favouritesListWithWeather</code>.</li>
    <li>Return <code>placeListWithWeather</code></li>
  </ol>
  
  <hr />
  
</details>
