### Pattern Guessing
Machine Learning changes this, for scenarios where you may not be able to figure out the rules feasibly, and instead have a computer figure out what they are.

steps that a computer takes -- where it makes a guess, then looks at the data to figure out how accurate the guess was, and then makes another guess and so on.

So, consider if I give you a set of numbers like this:
```
X: -1, 0, 1, 2, 3, 4
```
And then I give you another set of numbers like this:
```
Y: -3, -1, 1, 3, 5, 7
```
Can you figure out the relationship between the two sets? There’s a function that converts -1 to -3, 0 to -1, 1 to 1, 2 to 3, 3 to 5 and 4 to 7. Can you figure out the relationship.

if Y=3X-1, then
```
	X: -1, 0, 1, 2, 3, 4
```
Becomes
```
	Y: -4, -1, 2, 5, 8, 11

  Real Y = { -3, -1, 1, 3, 5, 7 }
```
Total that (∑) and take the square root √
```
  sqrt(1 + 1 + 4 + 9 + 16)

  = sqrt(31)
  = 5.57
```

what if it’s Y=2X-1?

Then, when you fill in the results for Y=2X-1, you’ll get:
```
X: -1, 0, 1, 2, 3, 4
Y: -3, -1, 1, 3, 5, 7
Real Y = {-3, -1, 1, 3, 5, 7}
Diff^2 = {1, 1, 1, 1, 1}
```
Get the same difference, repeat the same process.
```
sqrt(1 + 1 + 1 + 1 + 1)

= sqrt(5)
= 2.23
```
Make another guess! Y = 2X - 1
```
X = { -1, 0, 1, 2, 3, 4 }

My Y = { -3, -1, 1, 3, 5, 7 }
Real Y = {-3, -1, 1, 3, 5, 7}
Diff2 = {0, 0, 0, 0, 0}
```
#### Putting it together and coding

To use Keras, will need to have the TensorFlow package installed. See detailed instructions.

Once TensorFlow is installed, just import Keras via:
```
from tensorflow import keras
```

Complete code

```
from tensorflow import keras

model = keras.Sequential([keras.layers.Dense(units=1, input_shape=[1])])
model.compile(optimizer='sgd', loss='mean_squared_error')

xs = np.array([-1.0, 0.0, 1.0, 2.0, 3.0, 4.0], dtype=float)
ys = np.array([-3.0, -1.0, 1.0, 3.0, 5.0, 7.0], dtype=float)

model.fit(xs, ys, epochs=500)
print(model.predict([10.0]))

```
