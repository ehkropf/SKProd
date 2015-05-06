# SKProd
An implementation of the product formula for the Schottky-Klein prime function.

This function computes a truncated half Schottky group necessary
to calculate the truncated product formula for the Schottky-Klein
prime function. It returns a function handle which evaluates the prime
function. It's main interest is as a check against other code which
calculates the prime function.

Input:
  * dv = a vector of circle centers.
  * qv = a vector of circle radii.
  * L = (optional) truncation level of the product formula (default L=4).

Output:
  * wf = a function handle to the prime function with signature
    `w = wf(z, alpha)`,
  where z is an array of points at which to evaluate the function, and
  alpha is a scalar parameter value.

Example:
```
>> dv = [0.5, 0.5i];
>> qv = [0.1, 0.1];
>> wf = skprod(dv, qv, 6);
>> w = wf(-0.5-0.5i, 1);
>> w^2

ans =
  
           2.39754812001042 +      1.76164377385124i
```

This value may be checked against
  * D. G. Crowdy and J. S. Marshall, "Computing the Schottky-Klein prime
  function on the Schottky double of planar domains," CMFT 7 (2007) no.
  1, 293-308.

The prime function is documented in
  * H. Baker, Abelian Functions and the Allied Theory of Theta Functions,
  Cambridge University Press, Cambridge, 1897, 1995.
