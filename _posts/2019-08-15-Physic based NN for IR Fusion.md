---
layout: post
title:  "Physics based NN for IR Fusion"
date:   2019-08-15 11:18:36 -0700
---
# Approach
### Physics model
$$I(x)=J(x)t(x)+L_\infty(1-t(x))$$

### Our method
####DCP-guided residual learning
$$J^{dark} (x)=min$$

$$\begin{equation*}\label{eq4}%\vspace{-0.1cm}
\begin{split}
  &\min_\Theta \ell(\mathbf{J_{rec}}, \mathbf{J_{gt}})\\
  &s.t. \quad \mathbf{J_{rec}} = \mathop{\arg}\mathop{\min}_\mathbf{J} ~ \lambda\|f(\mathbf{J})-f(\mathbf{I_{NIR}})\|^2 + (1-\lambda)\|f(\mathbf{J})-f(\mathbf{I_{DCP}})\|^2 \\ & \quad\quad\quad\quad\quad\quad\quad\quad\quad + \mu \Phi(\mathbf{x}; \Theta) + \nu \Psi(\mathbf{J}; \mathbf{I_{NIR}})
\end{split}
\end{equation*}$$

![](images/RGBNIR Pictures.png)