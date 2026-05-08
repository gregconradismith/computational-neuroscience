---
title: "Information, representation, and physical computation"
kind: "page"
date: "1970-01-01"
slug: "information-and-physical-computation"
permalink: "/pages/information-and-physical-computation/"
render_with_liquid: false
---

<h2 class="wp-block-heading">Assignment</h2>


<p>Read Piccinini & Shagrir (2014). Foundations of computational neuroscience. Current Opinion in Neurobiology, 25, 25–30. <a href="https://www.sciencedirect.com/science/article/pii/S0959438813002043">Publisher</a> <a href="../../wp-content/uploads/2019/01/piccininishagrir2014foundationsofcomputationalneuroscience.pdf">PDF</a></p>


<p> There is no writing assignment on Blackboard, but the questions that appear throughout this page should help you prepare for class discussion.  </p>


<hr class="wp-block-separator has-alpha-channel-opacity" />


<h2 class="wp-block-heading">Summary</h2>


<p>The reading reiterates much of what we have discussed to date, but goes into more detail on the concepts of <em>information</em> and <em>physical computation</em>.  Piccinini and Shagrir repeatedly use neural integration by the oculomotor system as an example.  We will discuss "neural integrators" next week.  For now, let's ask ourselves the following.</p>


<h3 class="wp-block-heading">What is information?</h3>


<blockquote class="wp-block-quote">
<p><a href="https://en.wikipedia.org/wiki/Information">information</a> | ˌinfərˈmāSH(ə)n | as defined in the Oxford English Dictionary<br>noun<br>1 facts provided or learned about something or someone: <em>a vital piece of information</em>.... <br>2 what is conveyed or represented by a particular arrangement or sequence of things: <em>genetically transmitted information</em>.<br>• <span style="text-decoration: underline">Computing</span> data as processed, stored, or transmitted by a computer.<br>• (in information theory) a mathematical quantity expressing the probability of occurrence of a particular sequence of symbols, impulses, etc., as contrasted with that of alternative sequences.</p>
</blockquote>


<p>Perhaps we should add:</p>


<blockquote class="wp-block-quote">
<p><span style="color: #000000">• <span style="text-decoration: underline">Computational neuroscience</span> information is what is conveyed or represented by a particular case of neural activity or, more specifically, what is processed, stored or transmitted as the nervous system computes. </span></p>
</blockquote>


<p>The dynamic state of functioning nervous systems includes what our reading calls "variables" (time-varying observables) that <em>correlate</em> reliably with other variables, both internal and external.</p>


<p>This is enough to establish that nervous systems carry information in two senses.</p>


<p><strong><mark style="background-color:rgba(0, 0, 0, 0)" class="has-inline-color has-vivid-red-color">Mutual information</mark></strong>:  Some of the variables reduce uncertainty about other variables.  Using the mathematics of probability, the time-varying observables may be idealized as <em>random variables -- </em>note that the word "variable" has changed meaning! <em>-- </em>one may quantify the uncertainty that characterizes a process as a whole, by considering all of the possible alternative states.  This idea has its roots in Shannon's theory of communication, where the dynamic process is information transmission, and the states are the possible messages.</p>


<p>See Trappenberg, Thomas. <em>Fundamentals of Computational Neuroscience</em>. 2nd Edition. Oxford University Press <a href="https://global.oup.com/academic/product/fundamentals-of-computational-neuroscience-9780199568413?cc=us&lang=en&">Publisher</a>, 2010. <a href="https://www.amazon.com/dp/0199568413/">Amazon</a> <a href="../../wp-content/uploads/2019/01/trappenbergfundamentalscomputneuroappendixdbasicinformationtheory.pdf">Appendix D Basic information theory</a></p>


<p><strong><mark style="background-color:rgba(0, 0, 0, 0)" class="has-inline-color has-vivid-red-color">Semantic information</mark></strong> is a different concept.   Our reading states that...</p>


<blockquote class="wp-block-quote">
<p>Semantic information has to do with what a particular signal stands for or means. To capture the semantics of a signal, it is not enough to know which other signals might have been selected instead and with what probabilities. We also need to know what a particular signal stands for.... For example, a certain spike train in the oculomotor integrator makes it likely that a specific eye movement is about to occur.</p>
</blockquote>


<p><strong><mark style="background-color:rgba(0, 0, 0, 0)" class="has-inline-color has-vivid-red-color">Representation</mark></strong>:  Information would sometimes appear to be contained in nervous systems in the stronger sense of <i>representation, </i>whereby neural variables (observables) represent the environment as being a certain way.  Of course, there is the thorny philosophical issue of  <em>neural</em> versus <em>mental</em> representation.  Are these concepts equivalent?  If not, how do neural representations subserve mental representations?</p>


<h3 class="wp-block-heading">Physical computation</h3>


<p>Physical systems - e.g., digital computers - perform computations in the sense of information-processing. There is well-developed mathematical theory of computation (finite state machines, push-down automata, Turing machines, artificial languages, etc.) There is currently no corresponding theory of neural computation, but there is agreement that neural computing is physical computation that has different characteristics than the computations performed by digital computers. The best discussion of this topic I have found is Gualtiero Piccinini (2015). Physical Computation: A Mechanistic Account. Oxford University Press <a href="https://global.oup.com/academic/product/physical-computation-9780199658855">Publisher</a>. [SWEM <a href="https://wm-primo.hosted.exlibrisgroup.com/primo-explore/fulldisplay?docid=01COWM_WM_ALMA51742553070003196&context=L&vid=01COWM_WM_NEWUI&search_scope=01COWM_WM_ALMA&tab=01cowm_alma&lang=en_US">SWEM</a>] [Amazon <a href="https://www.amazon.com/dp/0198801165">Amazon</a>]</p>


<p>What makes nervous system activity a neural computation per se?  The authors suggest two possible views on this question.</p>


<p><strong><mark style="background-color:rgba(0, 0, 0, 0)" class="has-inline-color has-vivid-red-color">Modeling view of neural computation</mark></strong>: In the modeling view of neural computation, physical computation by the brain is a special <em>dynamic</em> form of representation that "models" target domain in the way that preserves higher order structure.  In this view, when we say that the nervous system computes, we are not necessarily saying anything about the mechanism by which this occurs.  For example, the "neural integration" performed by the oculomotor system is a computation.  Why?  Because within the oculomotor system (a physical system) the aspect of its dynamic state that represents eye velocity is maintained in its proper relation to the dynamic state of the oculomotor system that represents eye position.</p>


<p><strong><mark style="background-color:rgba(0, 0, 0, 0)" class="has-inline-color has-vivid-red-color">Mechanistic view of neural computation</mark></strong>: In the mechanistic view of neural computation, physical computation performed by the brain,</p>


<blockquote class="wp-block-quote">
<p>... is a specific kind of mechanistic process; it has to do with the processing of variables to obtain certain relationships between inputs, internal states, and outputs independently of how the variables are physically implemented, and this is so regardless of whether the variables carry any information about the environment.</p>
</blockquote>


<p>In the mechanistic view of neural computation there need not be any processing and transformations of neural representations.</p>


<hr class="wp-block-separator has-alpha-channel-opacity" />


<p>What are some examples of nervous system activity that are appropriately characterized as neural computation according to the <em>mechanistic view</em>, but that are probably not well-characterized as neural computation as defined by the <em>modeling view</em>?</p>


<hr class="wp-block-separator has-alpha-channel-opacity" />


<h2 class="wp-block-heading">Further reading</h2>


<p>McDonnell, M.D., Ikeda, S. and Manton, J.H., 2011. An introductory review of information theory in the context of computational neuroscience. <em>Biological cybernetics</em>, <em>105</em>(1), p.55. <a href="https://link.springer.com/article/10.1007/s00422-011-0451-9">Publisher</a></p>


<div class="a-section a-spacing-none">
<p id="title" class="a-spacing-none">Gualtiero Piccinini (2015). Physical Computation: A Mechanistic Account. Oxford University Press <a href="https://global.oup.com/academic/product/physical-computation-9780199658855">Publisher</a>. [SWEM <a href="https://wm-primo.hosted.exlibrisgroup.com/primo-explore/fulldisplay?docid=01COWM_WM_ALMA51742553070003196&context=L&vid=01COWM_WM_NEWUI&search_scope=01COWM_WM_ALMA&tab=01cowm_alma&lang=en_US">SWEM</a>] Especially Ch 15 Information Processing.</p>
<p><a href="https://www.amazon.com/dp/B00DGEQWBS">Robert M. Gray (2011).  Entropy and Information Theory.  2nd edition. Springer.</a></p>
</div>


<p>Newell, A., 1980. Physical symbol systems. Cognitive science, 4(2), pp.135-183. <a href="https://onlinelibrary.wiley.com/doi/abs/10.1207/s15516709cog0402_2">DOI</a></p>


<p>Piccinini, G., 2006. Computational explanation in neuroscience. <em>Synthese</em>, <em>153</em>(3), pp.343-353. <a href="https://link.springer.com/article/10.1007/s11229-006-9096-y">Publisher</a></p>
