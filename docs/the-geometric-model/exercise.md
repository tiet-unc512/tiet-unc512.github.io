
## Table of Contents

1.  [Exercises: The Geometric Model (VR Geometry)](#exercises-the-geometric-model-vr-geometry)
    1.  [Level 1: Easy (Foundational Concepts)](#level-1-easy-foundational-concepts)
    2.  [Level 2: Medium (Transformations & Rotations)](#level-2-medium-transformations-rotations)
    3.  [Level 3: Hard (Advanced Modeling & Kinematics)](#level-3-hard-advanced-modeling-kinematics)

<style>

.bvr-full-height-image-wrapper img {max-height: 30em}

</style>

[:material-file-pdf-box: Download this page as PDF](./exercise.pdf)


<a id="exercises-the-geometric-model-vr-geometry"></a>

## Exercises: The Geometric Model (VR Geometry)

Based on the concepts of 3D modeling, transformations,
and orientations for Virtual Reality.

--------------


<a id="level-1-easy-foundational-concepts"></a>

### Level 1: Easy (Foundational Concepts)

1.  **[TH]**{:.htag}
    Define a “Geometric Model” in the context of a
    Virtual World Generator (VWG).   
    **[SOL]**{:.htag}
    A mathematical description of the shape, size, and
    position of objects in a 3D virtual space.

2.  **[NM]**{:.htag}
    A point $P$ is located at $(2, 3, 5)$. If the
    model is translated by a vector $t = (1, -1, 2)$,
    what are the new coordinates of $P$?   
    **[SOL]**{:.htag}
    $(2+1, 3-1, 5+2) = (3, 2, 7)$.

3.  **[SB]**{:.htag}
    Explain why it is common to use triangles (meshes)
    to represent complex 3D objects instead of
    higher-order curved surfaces.   
    **[SOL]**{:.htag}
    Triangles are computationally efficient, always
    planar, and supported by GPU hardware.

4.  **[TH]**{:.htag}
    What are the three standard components of a 3D
    transformation (often abbreviated as TRS)?   
    **[SOL]**{:.htag}
    Translation, Rotation, and Scale.

5.  **[NM]**{:.htag}
    If a virtual world is defined in $\mathbb{R}^3$,
    what is the distance between point $A(1, 0, 0)$
    and point $B(4, 4, 0)$?   
    **[SOL]**{:.htag}
    $\sqrt{(4-1)^2 + (4-0)^2 + (0-0)^2} = 5$.

6.  **[TH]**{:.htag}
    Define the difference between “Global Coordinates”
    and “Local (Body) Coordinates.”   
    **[SOL]**{:.htag}
    Global: Fixed to world origin. Local: Fixed to the
    object; moves with it.

7.  **[SB]**{:.htag}
    In a VR engine, you see an option to “Parent” a
    sword to a character's hand. Based on geometric
    modeling, what does this imply about their
    coordinate systems?   
    **[SOL]**{:.htag}
    The sword's transform is relative to the hand's
    local coordinate system.

8.  **[NM]**{:.htag}
    Express a translation of 5 units along the x-axis
    and -3 units along the z-axis as a 3D translation
    vector.   
    **[SOL]**{:.htag}
    $t = (5, 0, -3)$.

--------------


<a id="level-2-medium-transformations-rotations"></a>

### Level 2: Medium (Transformations & Rotations)

9.  **[TH]**{:.htag}
    Explain why 2D rotations can be represented by a
    single angle $\theta$, whereas 3D rotations
    require more complex representations (like matrices
    or quaternions).   
    **[SOL]**{:.htag}
    2D has only one axis; 3D rotations are
    non-commutative (order matters).

10. **[NM]**{:.htag}
    Write the $3 \times 3$ rotation matrix
    $R_z(\theta)$ for a rotation of $90^\circ$
    around the Z-axis.   
    **[SOL]**{:.htag}
    $[[0, -1, 0], [1, 0, 0], [0, 0, 1]]$.

11. **[SB]**{:.htag}
    Discuss the phenomenon of “Gimbal Lock.” Which
    rotation representation is most susceptible to it,
    and why is it a problem for VR head tracking?   
    **[SOL]**{:.htag}
    Euler Angles. Occurs when two axes align, losing a
    degree of freedom.

12. **[NM]**{:.htag}
    Apply a $2 \times 2$ rotation matrix for $\theta
        = 45^\circ$ to the 2D point $(1, 0)$. (Hint:
    $\cos 45^\circ = \sin 45^\circ =
        \frac{1}{\sqrt{2}}$).   
    **[SOL]**{:.htag}
    $(\frac{1}{\sqrt{2}}, \frac{1}{\sqrt{2}})$.

13. **[TH]**{:.htag}
    What is a “Homogeneous Transformation Matrix,” and
    what is the primary advantage of using a $4 \times
        4$ matrix for 3D transformations?   
    **[SOL]**{:.htag}
    A matrix that allows translation to be treated as a
    multiplication, simplifying composition.

14. **[NM]**{:.htag}
    Given a rotation matrix $R$, prove that its
    transpose $R^T$ is equal to its inverse
    $R^{-1}$ (the Orthogonality property).   
    **[SOL]**{:.htag}
    $R \cdot R^T = I$ because rows/columns are
    orthonormal.

15. **[SB]**{:.htag}
    Compare the use of Euler Angles versus Quaternions
    for interpolating between two camera
    orientations. Why is one preferred for smooth
    movement?   
    **[SOL]**{:.htag}
    Quaternions allow for SLERP (Spherical Linear
    Interpolation), which is smoother.

16. **[TH]**{:.htag}
    Define “Yaw,” “Pitch,” and “Roll” in the context of
    an aircraft or a VR headset.   
    **[SOL]**{:.htag}
    Yaw: Y-axis; Pitch: X-axis; Roll: Z-axis.

--------------


<a id="level-3-hard-advanced-modeling-kinematics"></a>

### Level 3: Hard (Advanced Modeling & Kinematics)

17. **[NM]**{:.htag}
    A camera is located at $(0, 0, 0)$ looking toward
    the negative Z-axis. An object is at $(0, 0,
        -10)$. If the camera moves to $(5, 0, 0)$ and
    rotates $90^\circ$ around the Y-axis (looking
    toward the positive X-axis), what are the object's
    coordinates in the *camera's new local frame*?   
    **[SOL]**{:.htag}
    The object is now at local $(0, 0, 5)$ relative
    to the new camera orientation.

18. **[TH]**{:.htag}
    Describe the “Viewing Transformation.” List the
    steps required to move from a 3D world coordinate
    to a 2D coordinate on the screen.   
    **[SOL]**{:.htag}
    World $\rightarrow$ Eye $\rightarrow$ Canonical
    View $\rightarrow$ Screen.

19. **[NM]**{:.htag}
    Compose a single $4 \times 4$ homogeneous matrix
    that first rotates an object $30^\circ$ around
    the X-axis and then translates it by $(0, 10,
        0)$.   
    **[SOL]**{:.htag}
    $M = T \times R$ (Translation applied after
    rotation).

20. **[SB]**{:.htag}
    If a VR system has high latency in updating the
    “Geometric Model” relative to the user's head
    movement, describe the resulting visual artifacts
    and their impact on the user.   
    **[SOL]**{:.htag}
    “Judder” or latency lag, leading to motion
    sickness.

21. **[TH]**{:.htag}
    Explain the concept of “Double Covering” in the
    context of Unit Quaternions ($q$ and $-q$
    representing the same rotation).   
    **[SOL]**{:.htag}
    Two points on the 4D hypersphere represent one 3D
    rotation.

22. **[NM]**{:.htag}
    Convert the quaternion $q = ( \cos(\theta/2), 0,
        0, \sin(\theta/2) )$ back into its equivalent
    rotation matrix form.   
    **[SOL]**{:.htag}
    Result is the standard $R_z(\theta)$ matrix.

23. **[SB]**{:.htag}
    You are designing a VR “Mirror” where the user sees
    their avatar. Explain the geometric transformation
    required to reflect the avatar's movements across a
    plane $x = 0$.   
    **[SOL]**{:.htag}
    Reflection matrix where $x' = -x$.

24. **[NM]**{:.htag}
    Calculate the result of rotating point $v = (1, 0,
        0)$ by $180^\circ$ around the Y-axis using the
    quaternion formula $v' = qvq^{-1}$.   
    **[SOL]**{:.htag}
    $v' = (-1, 0, 0)$.

25. **[TH]**{:.htag}
    In the “Rendering Pipeline,” explain the role of
    the “Culling” process.   
    **[SOL]**{:.htag}
    Removing objects outside the Viewing Frustum to
    optimize performance.

--------------

*[TH]: Theoretical

*[NM]: Numerical

*[SB]: Subjective

*[SOL]: Solution itself or a hint.

