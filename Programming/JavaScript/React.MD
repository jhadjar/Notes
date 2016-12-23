Source: https://facebook.github.io/react/docs/introducing-jsx.html


```javascript

function formatName(user) {
  return user.firstName + ' ' + user.lastName;
}

// They don't use trailing commas in the tutorial. The stuff still works, though
// After a bit of research, it seems IE has difficulty with trailing commas.
// It may be useful to add a link on a page so IE users can download a browser.

const user = {
  firstName: 'Hodor',
  lastName: 'Just Hodor',
};


// They advise multiline JSX inside parentheses. It appears many don't do that.
// TODO: Search examples of real life code to learn about bad taste.
// Seems they're using braces. Templating style? Evaluate and render?

const element = (
  <h1>
    Hello, {formatName(user)}!
  </h1>
);

ReactDOM.render(
  element,
  element2,
  document.getElementById('root')
);


// JSX are expressions and become JavaScript objects after compilation.

function getGreetingUser(user) {
  if (user) {
    return <h1>Hello, {formatName(user)}!</h1>;
  }
  return <h1>Hello, Stranger.</h1>;
}

// In React, you're warm with users and cold with strangers. It's in the docs.

// The greeting is a bit redundant. Let's only return what changes.. 

function getGreetingUserBis(user) {
  if (user) {
    return formatName(user) + '!';
  }
  return "Stranger.";
}

const element2 = (
  <h1>
    Hello, {getGreetingUserBis(user)}
  </h1>
);

// Specify attributes with quotes

const element = <div tabIndex="0"></div>;

// Embed with curly braces:

const element = <img src={user.avatarUrl}></img>;
// or
const element = <img src={user.avatarUrl}/>;

// Don't abandon your children:

const element = (
  <div>
    <h1>Hello!</h1>
    <h2>Good to see you!</h2>
  </div>
);

// JSX is built with injection attacks in mind

const title = response.badMaliciousUserInput;
const element = <h1>{title}</h1>; // safe: escaped, converted, rendered.


// Representation

const element = (
  <h1 className="greeting">
    Hello, world!
  </h1>
);

//  is equivalent to:

const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, world!'
);

// this stuff is called "React elements"
```