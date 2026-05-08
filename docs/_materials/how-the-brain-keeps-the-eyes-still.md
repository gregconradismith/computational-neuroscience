---
title: "Line attractor networks (or how the brain keeps the eyes still)"
kind: "page"
date: "1970-01-01"
slug: "how-the-brain-keeps-the-eyes-still"
permalink: "/pages/how-the-brain-keeps-the-eyes-still/"
render_with_liquid: false
---
<h2>Preparation</h2>
Read Seung, H.S., 1996. How the brain keeps the eyes still. <em>PNAS</em> <em>93</em>(23):13339-13344. <a href="../../wp-content/uploads/2019/01/seung1996howbrainkeepseyesstill.pdf">PDF</a>
<div>
<h2>Overview</h2>
</div>
<blockquote>The brain can hold the eyes still because it stores a memory of eye position.  The brain's memory of horizontal eye position is stored by persistent neural activity in a network known as the "neural integrator," which is located in the brainstem and cerebellum.  The observed persistent patterns of activity can be interpreted from the perspective of dynamical systems as an attractive line of fixed points in the neural integrator's state space.  [Sebastian Seung, 1996; paraphrased]</blockquote>
Horizontal eye position is controlled by two extra ocular eye muscles (lateral and medial recti) that are innervated by motor neurons in the abducens and oculomotor nuclei, respectively.  Motor nuclei "read out" a memory of eye position that is stored in premotor areas, namely, the medical vestibular nucleus (MVN) and prepositus hyoglossi (PH).

"memory network" vs. "neural integrator":  When the head is still, the feedforward inputs to the network are constant, and the network is an autonomous dynamical system amenable to state space analysis.  This is the "how the brain keeps the eyes still" limit. During normal behavior, the network receives time-varying vestibular and visual input, and is a driven system rather than an autonomous one.  This is Robinson's "integrating with neurons" situation.

Seung discusses the state space portraits of the eye position memory network, modeled as a line attractor, while the read-out network flows toward a point attractor, the location of which is determined by the state of the memory network.

As in our previous reading by Robinson, Seung discusses how positive feedback changes the time constant of persistent activity.   Seung also discusses the issue of "fine tuning" and the idea that synaptic weights could be adjusted through a learning rule.
<h2>Linear attractor networks</h2>
The simplest network models are completely linear and a natural extension of the Wilson-Cowan formalism discussed last time. The mathematical formalism of attractor networks is summarized in this PDF <a href="../../wp-content/uploads/2019/02/attractornetworks.pdf">PDF</a>.

When a linear network is written in terms of firing rate, the Wilson-Cowan equations are

$latex \tau \frac{d\mathbf{v}}{dt} = - \mathbf{v} + W \mathbf{v} + \mathbf{f}&amp;s=4$.

Steady states are given by solutions of the following linear algebraic system:

$latex  (I-W) \mathbf{v} = \mathbf{f}&amp;s=4$

In the generic case, the matrix $latex  (I-W)&amp;s=1$ is full rank and, regardless of $latex  \mathbf{f}&amp;s=1$, there is only one solution, a fixed point given by

$latex   \mathbf{v} = (I-W)^{-1}\mathbf{f}&amp;s=4$

If the real part of the eigenvalues of $latex  (I-W)&amp;s=1$  are all negative, this is a globally asymptotically stable fixed point, i.e., the type of steady state Seung refers to as a <em>point attractor</em>.   Below is shown the firing rates of three neurons in a point attractor  network.  Regardless of initial condition, the same steady state is approached asymptotically.

[caption id="attachment_1842" align="alignnone" width="560"]<img class="alignnone size-full wp-image-1842" src="../../wp-content/uploads/2019/02/attractorpoint.png" alt="attractorpoint" width="560" height="420" /> Dynamics of a point attractor network.[/caption]

The special case of interest to Seung is when the matrix $latex  (I-W)&amp;s=1$ has rank $latex N-1&amp;s=1$ (i.e., its nullity is 1) and $latex  \mathbf{f}&amp;s=1$ is in the range of $latex  (I-W)&amp;s=1$.  One eigenvalue of $latex  (I-W)&amp;s=1$ is zero, while the other $latex N-1&amp;s=1$ eigenvalues are negative.  In this case, there are an infinite number of stable steady states arranged as a line (a <em>line attractor</em>).   Different initial conditions limit on this line, but not necessarily to the same point.

[caption id="attachment_1841" align="alignnone" width="560"]<img class="alignnone size-full wp-image-1841" src="../../wp-content/uploads/2019/02/attractorline.png" alt="attractorline" width="560" height="420" /> Dynamics of a line attractor network.[/caption]

Here is the matlab script that made the above figures.
<pre>% how the brain keeps the eyes still
% example linear network models

clear; close; clc

% n is number of neurons (you can change this)
n=4;

% the deficiency of rank you want
% point attractors when nullity=0
% line attractors when nullity=1
nullity=0;


dt = 0.001; % time step
tau = 1; % time constant

% construct random matrix of rank N minus nullity (this is M=-I+W)
% and make sure real part of eigenvalus is negative<span class="Apple-converted-space"> 
</span>M = zeros(n,n);
while any(real(eigs(M))&gt;=0)
   M = zeros(n,n);
   for i=1:n-nullity
      M = M + randn(n,1)*randn(1,n);
   end
end
% this makes sure b is in range of M
z = orth(M); b = z*randn(size(z,2),1);

for k=1:10 % number of initial conditions<span class="Apple-converted-space"> 
</span>   x = randn(n,1);
   for i = 1:1e5
      x(:,i+1) = x(:,i)+dt/tau*(M*x(:,i)+b); % M=-I+W
   end

   % only the 2 or 3 first dimensions are plotted
   % (x1, x2) if n=2, (x1, x2, x3) if n&gt;=3
   if n&lt;=2
      plot(x(1,:),x(2,:)); hold on;
      plot(x(1,end),x(2,end),'*','MarkerSize',10);
   else
      plot3(x(1,:),x(2,:),x(3,:),'LineWidth',2); hold on;
      plot3(x(1,end),x(2,end),x(3,end),'*','MarkerSize',10); hold on;
      zlabel('x3')<span class="Apple-converted-space"> 
</span>   end
   xlabel('x1')
   ylabel('x2')
end</pre>
<h2>Further reading</h2>
<div>
<div>The wikipedia page on <a href="https://en.wikipedia.org/wiki/Attractor_network">Attractor networks.</a></div>
<div></div>
</div>
<div><a href="https://www.sciencedirect.com/science/article/pii/S0893608098000641">Seung, H.S., 1998. Continuous attractors and oculomotor control. <i>Neural Networks</i>, <i>11</i>(7-8), pp.1253-1258.</a></div>
<div>

Seung, H.S., Lee, D.D., Reis, B.Y. and Tank, D.W., 2000. Stability of the memory of eye position in a recurrent network of conductance-based model neurons. <em>Neuron</em>, <em>26</em>(1), pp.259-271 <a href="https://www.sciencedirect.com/science/article/pii/S0896627300811551">Publisher</a>.

</div>
<div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
</div>
