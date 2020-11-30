#### Q1. Consider the following Javascript code:

```js
const a = (function () {
  return parseInt("1.5");
})();
```

What is the data type of `a`?

Select the best option:

- A. function
- B. object
- C. number <<<<--- Correct
- D. string

#### Q2. What's wrong with the following JavaScript code?

```js
const testString = "hello world";
const isAllCaps = false;
if (testString === testString.toUpperCase()) {
  isAllCaps = true;
}
```

Select the best option:

- A. `if` should be replaced with `while`
- B. === should be replaced with ==
- C. `const isAllCaps = false;` should be replaced with `let isAllCaps = false;` <<<<--- Correct
- D. Nothing is wrong, the code is bug free.

#### Q3. Consider the following Javascript code:

```js
let p1 = new Promise((resolve, reject) => {
  resolve("foo");
});
let p2 = new Promise((resolve, reject) => {
  reject("bar");
});

console.log("bip");

p1.then((val) => {
  console.log(val);
  return p2;
})
  .then((val) => {
    console.log("baz");
  })
  .catch((err) => {
    console.log(err);
  });

console.log("bop");
```

What is a possible output on the console?

Select the best option:

- A. ```
  bip
  bop
  foo
  bar

  ```
  <<<<--- Correct

  ```

- B. ```
  bip
  bop
  foo
  baz

  ```

  ```

- C. ```
  bip
  foo
  baz
  bop

  ```

  ```

- D. All of the above are possible due to the nondeterministic way Promises resolve

- E. None of the above

#### Q4. What is wrong with the following ES6 code?

```js
class MyList extends Array {
  constructor(someArg) {
    this.someArg = [...someArg];
  }
}

let theList = new MyList("foo");
```

Select the best option:

- A. `MyList` extends a built-in type, which is not allowed
- B. `super()` needs to be called in the constructor <<<<--- Corect
- C. The constructor for `Array` expects no arguments or an integer argument, but we are supplying a string argument
- D. `[...someArg]` will cause a syntax error because we are supplying a string to the constructor

#### Q5. What is the value of `a` after this cde runs?

```js
function foo(obj) {
  return {
    a: obj.bar,
    b: obj.baz,
  };
}
const { a } = foo({ bar: 27, baz: 41 });
```

Select the best option:

- A. `{ a: 27, b: 41 }`
- B. `27` <<<<--- Correct
- C. `undefined`
- D. An `Error` is thrown

#### Q6. Consider the following Javascript code.

```js
for (var i = 0; i < 5; i++) {
  setTimeout(function () {
    console.log(i);
  }, 100);
}
```

What is output to the console?

Select the best option:

- A. 0
  1
  2
  3
  4

- B. 5 <<<<--- Correct
  5
  5
  5
  5

- C. 0
  0
  0
  0
  0

- D. 5

- E. 4
  4
  4
  4
  4

#### Q7. What is the value of `k` after the following Javascript code runs?

```js
let i = 3;
let j = 4;
let k = 1;
for (i = 0; i < 3; i++) {
  k += j;
  j = j - 1;
}
```

Select the best option:

- A. `10` <<<<--- Correct
- B. `11`
- C. `13`
- D. `17`

#### Q8. You are building a social media product with users and followers. Consider the following code:

```js
class User {
  /**
   * @param {string} username
   * @param {Array.<string>} tags
   */
  constructor(username, tags) {
    this.username = username;
    this.tags = tags;
    this.followers = [];
  }

  /**
   * @param {User} user
   * @returns void
   */
  addFollower(user) {
    this.followers.push(user);
  }

  /**
   * Get the followers who are tagged with `tag`
   * @param {string} tag
   * @returns {Array.<User>}
   */
  getFollowers(tag) {
    // Fill in this line
  }
}
```

Fill in the missing line. Select `ALL` that are correct.

**Select all that apply:**

- A. ```js
  return this.followers.filter(
  (follower) => follower.tags.includes(tag)
  );

  ```<<<<--- Correct

  ```

- B. ```js
  return this.followers.includes(
  (follower) => follower.tags.filter(tag)
  );

  ```

  ```

- C. ```js
  return this.followers.filter(
  (follower) =>
  follower.tags.filter(
  (followerTag) => tag === followerTag
  ).length > 0
  );

  ```<<<<--- Correct

  ```

- D. ```js
  return this.followers.map(
  (follower) => follwer.tags.includes(tag)
  )
  ```

  ```

#### Q9. You are building a social network with influencers and their followers. You want to calculate the **reach** of a user. The **reach** is the number of users a given user can reach, given a certain degree of separation, including himself or herself. For example:

- At zero degrees of separation, the user can only reach himself or herself, so the reach is 1.
- At one degree of separation, the user can reach his/her direct followers plus himself/herself.
- At two degrees of freedom, the user can reach their direct followers, AND their followers' direct followers, plus himself/herself.

Fill in the missing line:

```js
class User {
  /**
   * @param {User[]} followers
   */
  constructor(followers) {
    this.followers = followers;
  }

  /**
   * The numbers of Users this User can reach with degreesOfSeparation hops,
   * including themselves
   * @param {number} degreesOfSeparation
   */
  getReach(degreesOfSeparation) {
    if (degreesOfSeparation <= 0) {
      return 1;
    }
    return (
      1 +
      this.followers
        .map((follower) => {
          // FILL IN THIS LINE
        })
        .reduce(function (a, b) {
          return a + b;
        }, 0)
    );
  }
}
```

Select the best option:

- A. `return 1;`
- B. `return follower.followers.length;`
- C. `return follower.getReach(degreesOfSeparation - 1);` <<<<--- Correct
- D. `return 1 + follower.getReach(degreesOfSeparation - 1);`

#### Q10. In CSS, what is the difference between `.foo` and `#foo`?

Select the best option:

- A. `#foo` is a hash fragment for a URL while `.foo` references a property named `"foo"`
- B. `.foo` selects block elements, while `#foo` selects inline elements.
- C. `.foo` selects by class while `#foo` selects by id <<<<--- Correct
- D. `.foo` is a valid CSS selector while `#foo` is not
- E. `.foo` and `#foo` are equivalent
