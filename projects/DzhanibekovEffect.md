<script type="text/x-mathjax-config">
  MathJax.Hub.Config({
    tex2jax: {
      inlineMath: [ ['$','$'], ["\\(","\\)"] ],
      processEscapes: true
    }
  });
</script>
    
<script type="text/javascript"
        src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>

# Dzhanibekov Effect

The Dzhanibekov effect is a phenomenon in which a rotating rigid body exhibits unexpected motion due to its moments of inertia. The effect is a result of the intermediate axis theorem, which states that a rigid body rotating about its intermediate axis is unstable.

![Dzhanibekov Effect](2to1top.gif)
*The Dzhanibekov effect demonstrated in my simulation with a simple 3D model subjected to angular momentum.*

To acheive this effect, I first implemented an **[algorithm to compute an interia tensor for any closed mesh.](https://citeseerx.ist.psu.edu/document?repid=rep1&type=pdf&doi=08b2ce791f24002743ba45ef1b2d35a4accb4a7c)** The inertia tensor is a 3x3 matrix that describes how mass is distributed in a rigid body. The solver uses the **[intertia tensor](https://w.wiki/DJnY)** and angular momentum to compute the angular acceleration of the body. The angular acceleration is then converted to a **[quaternion](https://en.wikipedia.org/wiki/Quaternion)**, then integrated to update the orientation of the body.

This effect is a result of Euler's equations of motion for a rigid body:

$$
I \dot{\omega} + \omega \times (I\omega) = 0
$$

This numerical simulation was rendered using a custom 3D rendering engine written in C++. The effect is most notable when the body is not subjected to gravity or other external forces, as shown in the simulation.

![Dzhanibekov Effect in Space](spacedemo.gif)
*The Dzhanibekov effect demonstrated aboard a space station.*