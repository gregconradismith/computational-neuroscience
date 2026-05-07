---
title: "Neural integrators (e.g., the vestibulo-ocular reflex and head direction cells)"
kind: "page"
date: "1970-01-01"
slug: "oculomotor-system"
permalink: "/pages/oculomotor-system/"
render_with_liquid: false
---
<!-- wp:heading -->
<h2 class="wp-block-heading">Preparation for class Thursday, February 13</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Read pp. 165-172 of Goldman, Compte, and Wang (2009). Neural Integrator Models. [\[PDF\]](../../wp-content/uploads/2019/01/Goldmanetal_NeuralIntegrators.pdf) This reading discusses neural integrators more generally. Focus on understanding Figures 1-5.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 class="wp-block-heading">Preparation for class Tuesday, February 18  </h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Read pp. 376-385 of Baer, Connors, and Paradiso (The Auditory and Vestibular Systems). [\[PDF\]](../../wp-content/uploads/2025/02/baeretalneurosciencech11auditoryandvestibularsystems.pdf)</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Read pp. 33-38, 42-44 of Robinson (1989). Integrating with neurons. Annu Rev Neurosci. 12:33-45. [\[PDF\]](../../wp-content/uploads/2019/01/robinson_integratingwithneurons.pdf) The page range indicates that you may skip the *Models of Neural Integrators* section, which we talked about already.</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<!-- wp:heading -->
<h2 class="wp-block-heading">Overview</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>The introduction of Robinson 1989 discusses integration in <em>control systems</em> and the expectation (of bioengineers entering the field of neuroscience) that <em>neural integrators</em>&nbsp;and/or <em>negative feedback</em>&nbsp;would be found in the neural systems controlling eye position.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Robinson and others did indeed discover a neural integrator that whose performance is important for the proper function of the <a href="https://en.wikipedia.org/wiki/Vestibulo–ocular_reflex">vestibulo-ocular reflex</a>.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center"} -->
<figure class="wp-block-image aligncenter"><img src="https://upload.wikimedia.org/wikipedia/commons/9/99/1608_Vestibulo-Ocular_Reflex-02.jpg" alt="" /><figcaption class="wp-element-caption">From Anatomy &amp; Physiology, Connexions Web site. <a class="external free" href="http://cnx.org/content/col11496/1.6/" rel="nofollow">http://cnx.org/content/col11496/1.6/</a></figcaption></figure>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>The same neural integrator is involved in <em>saccadic eye movements</em>. &nbsp;In both cases, neural activity that is proportional to "velocity" of the eye is converted into neural activity that is proportional to "position" of the eye.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Goldman, Compte, and Wang 2009 discuss neural integrators more generally, using the vestibulo-occular reflex as one example. &nbsp;Another example are <a href="https://en.wikipedia.org/wiki/Head_direction_cells">head direction cells</a> that integrate velocity signals emanating from the vestibular system. &nbsp;Goldman, Compte, and Wang 2009 use the VOR systems and head direction cells as examples of neural integrators exhibiting a "rate code" versus a "location code."</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p><strong>Think about:</strong><em> Which of these examples of neural "coding" (rate code versus location code) best illustrates the idea of neural representation?</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Both of the required readings use differential equations to describe the activity of a population of neurons that exhibit <em>recurrent excitatory connections</em>. &nbsp;The equations written are examples of <em>Wilson-Cowan population activity models</em>, which describe</p>
<!-- /wp:paragraph -->

<!-- wp:quote -->
<blockquote class="wp-block-quote"><!-- wp:paragraph -->
<p>... the evolution of excitatory and inhibitory activity in a synaptically coupled neuronal network. As opposed to being a detailed biophysical model, [these equations are] a coarse-grained description of the overall activity of a large-scale neuronal network.... Key parameters in the model are the strength of connectivity between each subtype of population (excitatory and inhibitory) and the strength of input to each subpopulation. Varying these generates a diversity of dynamical behaviors that are representative of observed activity in the brain, like multistability, oscillations, traveling waves, and spatial patterns. (From Kilpatrick 2013. Wilson-Cowan model. [\[PDF\]](https://www.colorado.edu/amath/sites/default/files/attached-files/kilpatrick_wc14.pdf) Encyclopedia of Computational Neuroscience.)</p>
<!-- /wp:paragraph --></blockquote>
<!-- /wp:quote -->

<!-- wp:paragraph -->
<p>Some mathematical explanation for the form of these equations is provided in these notes on Wilson-Cowan-type equations [\[PDF\]](../../wp-content/uploads/2019/01/wilsoncowan.pdf), The readings also discuss how the integration time constant for recurrent excitatory networks is longer than the time constant for the decay of neural activity in the absence of recurrent excitation. These notes show how postive feedback changes time constant of leaky integrator. [\[PDF\]](../../wp-content/uploads/2019/01/postivefeedback.pdf)</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p></p>
<!-- /wp:paragraph -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity" />
<!-- /wp:separator -->

<!-- wp:syntaxhighlighter/code {"language":"matlabkey","lineNumbers":false} -->
<pre class="wp-block-syntaxhighlighter-code">% Two-unit neural network for the integrator of the oculomotor system
% 
% Greg Conradi Smith
% 
% Written for APSC 450 Computational Neuroscience in Spring 2023
% 
% Refernce: Cannon SC, Robinson DA, and Shamma S (1983). A proposed neural
% network for the integrator of the oculomotor system
% 
% Background: Goldman, M. S., Compte, A., &amp; Wang, X. J. (2009). Neural
% integrator models. Encyclopedia of neuroscience, 165-178.

clear; clc; close all
set(0, 'DefaultAxesFontSize', 18);

dt = 0.01;
total = 300;

tau = 5;
ws=1; wsmw=-0.9999; w=ws-wsmw;
vs=1; vsmv=0.1; v=vs-vsmv;

t = [0:dt:total];
[x1,x2, du] = deal(zeros(length(t),1));
du(find(t&gt;30&amp;t&lt;50))=1;
du(find(t&gt;100&amp;t&lt;120))=1;
du(find(t&gt;200&amp;t&lt;240))=-1;
u1=du; u2=-du;
for i=2:length(t)
    x1(i) = x1(i-1) + dt*( -(1+ws)*x1(i-1)-w*x2(i-1) + ...
        vs*u1(i-1)+v*u2(i-1) )/tau;
    x2(i) = x2(i-1) + dt*( -w*x1(i-1)-(1+ws)*x2(i-1) + ...
        v*u1(i-1)+vs*u2(i-1) )/tau;
end

figure(1)
subplot(2,1,1)
plot(t,x1,'r',t,x2,'g--','LineWidth',2)
ylabel('position')
legend({'x1','x2'})

subplot(2,1,2)
plot(t,u1,'r',t,u2,'g--','LineWidth',2)
ylabel('input')
xlabel('time (ms)')
legend({'u1','u2'})
</pre>
<!-- /wp:syntaxhighlighter/code -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity" />
<!-- /wp:separator -->

<!-- wp:image {"id":3294,"sizeSlug":"large","linkDestination":"none"} -->
<figure class="wp-block-image size-large"><img src="../../wp-content/uploads/2023/02/three_pulse_fig1.png" alt="" class="wp-image-3294" /></figure>
<!-- /wp:image -->

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity" />
<!-- /wp:separator -->

<!-- wp:heading -->
<h2 class="wp-block-heading">Further reading</h2>
<!-- /wp:heading -->

<!-- wp:list -->
<ul class="wp-block-list"><!-- wp:list-item -->
<li>Arnold and Robinson (1992). A neural network model of the vestibulo-ocular reflex using a local synaptic learning rule. Philos Trans R Soc Lond B Biol Sci. 337(1281):327-30. [\[PDF\]](../../wp-content/uploads/2019/01/arnold1992aneuralnetworkmodlofvor.pdf)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Destexhe, A. and Sejnowski, T.J., 2009. The Wilson–Cowan model, 36 years later. *Biological cybernetics*, *101*(1), pp.1-2. [\[PDF\]](../../wp-content/uploads/2019/01/sejnowskidestexhe2009thewilson-cowan_model_36_years_later.pdf)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Cannon, Robinson and Shamma (1983). A proposed neural network for the integrator of the oculomotor system. Biol Cybern. 49(2):127-36. [\[PDF\]](../../wp-content/uploads/2019/01/cannonetal1983.pdf)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Branoner, F., Chagnaud, B. P., & Straka, H. (2016). Ontogenetic development of vestibulo-ocular reflexes in amphibians. *Frontiers in neural circuits*, *10*, 91. [\[PDF\]](../../wp-content/uploads/2019/01/front._neural_circuits_2016_branoner.pdf)</li>
<!-- /wp:list-item -->

<!-- wp:list-item -->
<li>Angelaki, D. E. (2004). Eyes on target: what neurons must do for the vestibuloocular reflex during linear motion. *Journal of neurophysiology*, *92*(1), 20-35. [\[PDF\]](../../wp-content/uploads/2019/01/jneurophysiol2004angelaki.pdf)</li>
<!-- /wp:list-item --></ul>
<!-- /wp:list -->

<div class="embed-youtube">
<iframe title="YouTube video" src="https://www.youtube.com/embed/YMIMvBa8XGs" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</div>

<!-- wp:separator -->
<hr class="wp-block-separator has-alpha-channel-opacity" />
<!-- /wp:separator -->
