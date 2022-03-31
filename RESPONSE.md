### Question 1

La Fonction prend en paramètres les intervalles si il y a des intersections elle retourne par nombre croissant l'union des intervales sinon elle retourne les intervales (Merge des intervales)

### Question 2

```javascript
function foo(intervals) {
  if (intervals.length === 1) return intervals;
  intervals.sort((a, b) => a[0] - b[0]);
  let current = intervals[0];
  const result = [current];
  for (let i = 1; i < intervals.length; i += 1) {
    const currentRight = current[1];
    const [nextLeft, nextRight] = intervals[i];
    if (currentRight >= nextLeft) {
      current[1] = Math.max(currentRight, nextRight);
    } else {
      result.push(intervals[i]);
      current = intervals[i];
    }
  }
  return result;
}

console.log(
  foo([[0, 3], [6, 10]]),
  foo([[0, 5], [3, 10]]),
  foo([[0, 5], [2, 4]]),
  foo([[7, 8], [3, 6], [2, 4]]),
  foo([[3, 6], [3, 4], [15, 20], [16, 17], [1, 4], [6, 10], [3, 6]])
)
```

Solution testée sur codesandbox

### Question 3

la résolution du problème m'a pris 2h et j'ai trouvé la solution sur Youtube aussi en toute transparence 
https://www.youtube.com/watch?v=hbPATy78Rss