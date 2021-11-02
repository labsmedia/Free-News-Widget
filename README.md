# Newbly-News-Widget


```javascript
function iframeInit() {
  const newblyLanguage = 'english'; // currently available languages - turkish, romanian, serbocroatian, arabic, english
  const newblyCountry = 'austria'; // currently available countries - austria
  const newblyCategories = 'politics,economics,chronicle'; // currently available categories (specify without spaces) - politics, economics, chronicle, sport, culture, health
  const articlesPerCategory = 2;
  const parentContainerId = 'app'; // <div id="my-id"> ... widget will go here ... </div>
  const iFrameWidth = '100%';
  const iFrameHeight = '550px';
  const layout = 'horizontal'; // available options - horizontal, vertical (default)
  const autoPlaySpeed = '15000'; // available for horizontal layout
  const autoPlay = 'true'; // available for horizontal layout
  const animationSpeed = '2000'; // available for horizontal layout
​
  // regular css
  const newblyStyle = `
      .newbly-widget-container h2 {
          color: black;
      }
      .newbly-widget-container p:hover {
          color: lightBlue;
          cursor: pointer;
      }
    `;
​
  // all available css classes
​
  /* const exampleStyle = `
      .newbly-widget-container {}
      .newbly-widget-container h2 {}
      .newbly-widget-container h3 {}
      .newbly-widget-container p {}
      .newbly-widget-container a {}
      .widget-error-message {}
      .widget-article-separator {}
      .widget-footer {}
      .widget-footer > span {}
      .widget-logo {}
      .widget-logo > span {}
    `; */
​
  /* Dont edit code below */
​
  const encodedCss = window.btoa(newblyStyle); // encode a string
  const container = document.getElementById(parentContainerId); // get parent container
  if (!container) {
    console.warn("Parent container id not specified or it doesn't exist");
    return;
  }
  let iframe = document.createElement('iframe'); // create iframe
  // set attributes for iframe
  iframe.setAttribute(
    'src',
    `https://newb.ly/widget/newsfrom/${newblyCountry}/in/${newblyLanguage}/?categories=${newblyCategories}&amount=${articlesPerCategory}&layout=${layout}&css=${encodedCss}&autoPlaySpeed=${autoPlaySpeed}&autoPlay=${autoPlay}&animationSpeed=${animationSpeed}`
  );
  iframe.setAttribute('frameborder', 'no');
  iframe.style.width = iFrameWidth;
  iframe.style.height = iFrameHeight;
  iframe.style.borderWidth = 0;
  container.appendChild(iframe); // attach to the dom
}
```
