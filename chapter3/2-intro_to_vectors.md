# Vectors

In mathematics, a vector is a list of elements. A single element on its own is known as a scalar. A vector is basically a one-dimensional array of elements.

With GLM, you can create a vector as follows:

```c++
vec4 vec(0.0f, 0.0f, 0.0f, 0.0f);
```

Vectors can be of any size, but in graphics programming, only vectors of lengths 2 to 4 are commonly used, so those are the only ones included in GLM.

Mathematic notation for vectors is as follows:

![Vector notation](images/2-vector_notation.svg)

In order, a vector's elements can be referred to as: X, Y, Z, and W. X, Y, and Z are positions in 3D space. W is different; it is known as the **homogenous vertex coordinate**. It isn't important for now, but will be discussed later.

So, what can you do with a vector? Let's start with basic vector arithmetic.

## Scalar operations

Scalar operations refer to any operation that uses both a scalar (a single element) and a vector (multiple elements). Simply put, the scalar is applied to each element of the vector separately. For example:

![Scalar operations](images/2-scalar_operation.svg)

It works exactly the same for subtraction, multiplication, and division.

## Vector operations

Vector operations are any operation that uses two vectors. The operation is applied to each element of the vector (X with X, Y with Y, etc.).

![Vector operations](images/2-vector_operation.svg)

Vector operations are only allowed when both vectors are of the same length. For example, you can't add a vector with a length of 2 to a vector with a length of 4.
