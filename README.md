## Famous Quotes
This first quote by [Heinrich Heine](https://www.brainyquote.com/authors/heinrich-heine-quotes) frames the notion of experience as a double edged sword:
> Experience is a good school. But the fees are high.

---

The second [quote](https://www.brainyquote.com/quotes/carl_jung_114802) by Carl Jung tells us there still can be things we dont know about ourselves:
> Everything that irritates us about others can lead us to an understanding of ourselves.

## Fetch
This dog really wants the ball and its a silly picture.
![Dog in pool fetching a ball](https://external-preview.redd.it/yaQQ7wHxtBtKBdk3mSvSCGULfpnJkus1lnCYJEFGRE4.jpg?auto=webp&s=730a45997b85ec73a759e785b29d2f76fe38923a)

## Tables are Fun

| Text                    | **Simplified Text (_In Italics_)** |
| ----------------------- | ---------------------------------- |
| Due to the fact that    | _because_                          |
| In the event that       | _if_                               |
| At this point in time   | _currently_                        |
| Obtain                  | _get_                              |
| Subsequent              | _following_                        |
| In the vicinity of      | _around_                           |

### Conciseness Helps Web Readers

Nobody like to read long blocks of texts. Clear, short text saves the readers time.

At this point in time we can’t ascertain the reason as to why the screen door was left open.

`Currently, we don't know why the screen door was left open.`

There is a desire on the part of many of us to maintain a spring break for the purpose of getting away from the demands of our studies.

`Many of us wants to keep spring break so that we may be freed from our studies.`

## Code Blocks Make Me Happy


Here's a JavaScript code snippet for solving second degree quadratic equations
```javascript
/**
 * Solves quadratic ( ax^2 + bx + c = 0 ) with Po-Shen method
 * @param {Number} a quadratic coefficient
 * @param {Number} b linear coefficient
 * @param {Number} c constant 
 */
function quadratic(a, b, c) {
  const denominator = a;
  let sum = -b;
  let halfSum = sum / 2;
  let constant = c;

  if (denominator !== 1) {
    sum /= denominator;
    halfSum = sum / 2;
    constant /= denominator;
  }

  const square = halfSum ** 2;
  const equ = square - constant;
  const rootEqu = Math.sqrt(equ);

  const ansPos = halfSum + rootEqu;
  const ansNeg = halfSum - rootEqu;

  return { "positive": ansPos, "negative": ansNeg };
}
```

Here's the bash command for generating a RSA2048 key pair that expires after a year.
```bash
user=$(whoami)
openssl req -nodes -x509 -newkey rsa:2048 -keyout "$user".key -out "$user"-cert.pem -days 365 -nodes
```

**Finally Finished**