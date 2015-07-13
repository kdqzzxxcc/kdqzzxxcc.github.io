---
layout: post
category : 学习
tags : [OPP][math]
---
#Orthogonal Procrustes problem

##描述
有矩阵A,B找到一个最佳的矩阵T，使得A经过正交矩阵T旋转之后，它的Frobenius norm of error AT-B 最小。
$$A,B\in R^{m*n},T\in R^{n*n}$$
$$min_T ||B-AT||_{F}$$
$$s.t.  T'T=I$$
where$$||*||_{f}$$ denotes the Frobenius norm

##求解
参考[1].
$$E=AT-B$$
$$g_{1}=tr(E'E=T'A'AT-2T'A'B+B'B)$$
$$g_{2}=tr(L(T'T-I))  其中L是拉格朗日乘子$$
$$g=g_{1}+g_{2}$$
$$\partial g/\partial T=2A'AT-2A'B+T(L+L')=0$$
$$A'AT+1/2T(L+L')=A'B$$
$$另P=A'A,Q=1/2(L+L'),S=A'B,则PT+TQ=S$$
$$SS'=WD_sW',S'S=VD_SV',其中W'W=WW'=V'V=VV'=I$$
$$S=WD_S^{1/2}V'$$
$$WD_SW'=TVD_SV'T'=>W=TV=>T=WV'$$
$$则解得W,V即可得T(W,V可以通过SVD(S)解得)$$

##参考
P.Schonemann,A  GENERALIZED  SOLUTION  OF  THE ORTHOGONAL  PROCRUSTES  PROBLEM,PSYCHOMETRIKA--31,1966 
