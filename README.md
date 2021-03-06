# FaceMorph
Simple Python script that contains functions for morphing one face into another.

## How
1. Find [face landmarks](http://blog.dlib.net/2014/08/real-time-face-pose-estimation.html).
1.5. Adjust the tone of the source face to approximately match the tone of the target face.
2. Map the landmarks points to each other.
3. Find the Delauney triangulation of the landmarks from the source image.
4. For each triangle in the source image, (affine) transform it to its corresponding one in the destination image.
5. You can interpolate how much the face is morphed (0 for no morph, 1 for full morph).

## Can you show me some examples?
Sure:

|      Applying makeup      |       Removing makeup       |
| ------------------------- | --------------------------- |
| ![apply1](gif/apply1.gif) | ![remove1](gif/remove1.gif) |
| ![apply2](gif/apply2.gif) | ![remove2](gif/remove2.gif) |

Also, below are some nightmarish examples where the morphing is mixed between two persons:

|      Applying makeup      |       Removing makeup       |
| ------------------------- | --------------------------- |
| ![apply3](gif/apply3.gif) | ![remove3](gif/remove3.gif) |
| ![apply4](gif/apply4.gif) | ![remove4](gif/remove4.gif) |

## Dependencies
You should have `numpy` (for image manipulation) and `cv2` (for triangulation).
Also, `face_recognition` is needed to find the face landmarks (you can use another library if you want).
Please note that `face_recognition` requires `dlib`, which can be annoying to set up.
Finally, `matplotlib` is needed to make the videos in this README.
