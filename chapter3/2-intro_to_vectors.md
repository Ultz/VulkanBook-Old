# Vectors

In mathematics, a vector is a list of elements. A single element on its own is known as a scalar. A vector is basically a one-dimensional array of elements.

With GLM, you can create a vector as follows:

```c++
vec4 vec(0.0f, 0.0f, 0.0f, 0.0f);
```

Vectors can be of any size, but in graphics programming, only vectors of sizes 2 to 4 are commonly used, so those are the only ones included in GLM.

Mathematic notation for vectors is as follows:

![Vector notation](images/2-vector_notation.svg)

In order, a vector's elements can be referred to as: X, Y, Z, and W. X, Y, and Z are positions in 3D space. W is different; it is known as the **homogenous vertex coordinate**. It isn't important for now, but will be discussed later.

So, what can you do with a vector? Let's start with basic vector arithmetic.

## Scalar operations

Scalar operations refer to any operation that uses both a scalar (a single element) and a vector (multiple elements). Simply put, the scalar is applied to each element of the vector separately. For example:

![Scalar operations](images/2-scalar_operation.svg)

It works exactly the same for subtraction, multiplication, and division.

In GLM:

```c++
vec2 = vec1 + 3;
```

## Vector operations

Vector operations are any operation that uses two vectors. The operation is applied to each element of the vector (X with X, Y with Y, etc.).

![Vector operations](images/2-vector_operation.svg)

Vector addition and subtraction work the same way, but multiplication (and division, which is a form of multiplication) are different; see 3.3: Vector Products. Vector operations are only allowed when both vectors are of the same size. For example, you can't add a vector with a size of 2 to a vector with a size of 4.

In GLM:

```c++
vec3 = vec1 + vec2;
```

## Length of vectors

The length of a vector is something very important to know for several different reasons. The length of a vector is notated as follows:

![Vector length notation](images/2-vector_length_notation.svg)

Luckily, it's not hard to figure out. You can think of the X and Y coordinates as being the height and width of a triangle, like so:

<img src="images/2-vector_length_notation.svg" alt="X and Y as width/height" width="400" height="400">

Using this example, the length would be the hypotenuse of the triangle. To find this, you can use what's known as the Pythagorean Theorem. This is a very simple operation, just do the following:

1. Square all of the elements.
2. Add all the elements together.
3. Square root the result.

On paper, it looks like this:

![Pythagorean Theorem](images/2-pythagorean_theorem.svg)

In GLM:

```c++
glm::length(vec);
```

## Unit vectors

A unit vector (sometimes called a normalized vector) is any vector whose length is exactly 1. Every vector has a non-zero unit vector, which can be found by dividing a vector by its length:

![Finding unit vector](images/2-finding_unit_vector.svg)

The unit vector is simple to find, but it is used in many different formulas. One major one will be discussed in the next section.

In GLM:

```c++
glm::normalize(vec);
```
