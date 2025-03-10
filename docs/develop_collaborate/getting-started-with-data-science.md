<html>

<body>
    <p>
Data science has exploded in popularity (and sometimes, hype) in recent years. This has led to an increased interest in learning the subject, which is a loose collection of topics rather than a coherent field. It encompasses topics like data storage (databases, data storage technologies), data engineering (infrastructure and techniques for transforming data at scale), statistics and machine learning, data visualization and communication, and many other topics. For a beginner, it is crucial to get a flavor of the subject before diving deep and specializing. The following text is an off-the-cuff and informal response written to someone curious about learning data science.
</p>

<ol>
<li> In terms of programming languages, python is used heavily in industry and in computer science departments (where a lot of ML research happens). R is used heavily by groups doing "classical" statistics e.g. statistics, medicine/clinical groups, psychology etc. R has a very rich set of libraries in this arena while python is still lacking (although there are packages like statsmodels). When it comes to ML, especially deep learning, reinforcement learning etc., python dominates and I don't know of anyone who uses R for these. Here python is almost always used as a prototyping language with all the core functionality implemented in a lower-level language (C, C++, numerical routines in Fortran). So, a practitioner might write a neural network using PyTorch or numpy which, in turn, call parallelized SIMD or GPU-based operations implemented in lower-level languages. An interesting alternative language is Julia but if you are starting out, I would stick to python and/or R. </li>

<li> The day-to-day work of data scientists can be vastly different. The situation is analogous to being a "software engineer". Person A might be a low-level kernel hacker while Person B might be writing front-end code in React. Same job title, very different skill sets even though both can write code.

There are a few things you could try to get a flavor of data science:

<ul>
<li>Machine Learning (ML): The classic course used to be <a href=https://www.coursera.org/learn/machine-learning>Andrew Ng's Coursera course</a>. I would still highly recommend it. In addition, I would recommend understanding the mathematics carefully and slowly, and implementing not just the assignments but each algorithm from scratch in python. This will help you get a flavor for how one approaches models in ML. You might never touch the mathematics again but it'll give you an appreciation for the design and analysis of ML algorithms.</li>

<li>Data Manipulation: A huge part of data science jobs is getting the data in the right structure and format as well as exploring and checking ideas in the dataset. R has amazing libraries (<a href="https://dplyr.tidyverse.org/">dplyr</a>) for this and in the python world, <a href="https://pandas.pydata.org/">pandas</a> essentially replicated these functionalities. Similarly, getting comfortable with any plotting library (e.g. <a href="https://matplotlib.org/">matplotlib</a>, <a href="https://seaborn.pydata.org/">seaborn</a>, <a href="https://plotly.com/">plotly</a>) will be very useful. <a href="https://numpy.org/">Numpy</a> is another essential python package and a general principle is to replace as many loops in your code by highly-optimized numpy functions as possible. The best way to learn these skills is to pick a dataset from your job or from <a href="https://www.kaggle.com/">kaggle</a> and start using pandas and matplotlib to explore patterns/hypotheses.</li>

<li>Kaggle: A good way to apply ML/modelling skills is to pick a <a href="https://www.kaggle.com/competitions">kaggle problem</a>. Do pick one that has a tabular dataset and not images, text etc. if it's your first modelling exercise. Building models for a specific task that can be scored is a great way to learn new modelling techniques. A downside of kaggle is that most real world problems are not that well-defined and don't require getting an extra 0.001% accuracy. Models on kaggle tend to be too complicated (an ensemble of 50 models, for example) but even with these caveats, kaggle is a great way to learn practical modelling.</li>

<li>Data Pipelines: This is arguably what a data engineer does but most data scientists now interact with some pipelining infrastructure. You can look up <a href="https://www.operate-first.cloud/">operate-first</a> at Red Hat which has <a href="https://www.kubeflow.org/docs/components/pipelines/introduction/">Kubeflow pipelines</a> installed. One can specify these pipelines in python using a <a href="https://www.kubeflow.org/docs/components/pipelines/sdk/sdk-overview/">domain-specific language</a> and execute large jobs in parallel. This is a crucial part of a data scientist's job since they generally come up with data transformations and having the ability to execute these workflows on large datasets is critical. </li></ul></li>

<li> <p>The other crucial part that many people discount is their own domain expertise. Many data scientists get stuck at step 2. They know enough techniques and programming but have a hard time going deep into a problem. All problems then seem to have the same flavor: get a CSV file, make some plots, train a simple model and show it to someone who says "eh? that's not very useful" and nothing happens. Rinse and repeat. </p>

<p>A big reason for this is the lack of domain knowledge/expertise. In almost every scientific field, the data scientist is actually a physicist, chemist, psychologist, mathematician (numerical experiments) etc. who has a deep understanding of their field and picks up the necessary techniques to analyze their data. They have a set of questions they want to ask and they have the knowledge to interpret the results of their models and experiments. A problem with being a data scientist without that expertise is that all the focus falls on the techniques and not the actual questions. It strips away the ability to generate new experiments. The only solutions are to either work with an expert or even better, to start learning the field one is interested in. This does take a long time but pays rich dividends.</p>

<p>So, going at this the other way, i.e. where one knows a field and learns skills from point 2., can be very powerful.</p></li>

<li> In many cases, there's also the option of going deep into the techniques. A big caveat is that some of these are very specialized and generally need a lot of dedicated time. Also, most industrial data scientists will never touch most of what's below. Note that the list below is woefully incomplete.

<ul>
    
<li> Deep Learning: learning not just the basics of neural networks and their architectures but learning to design new ones. Understanding the tradeoffs in their design. Getting comfortable with the tools e.g. PyTorch, GPU kernels, possibly some C, Julia code etc. that let one carry out diverse experiments and scale them. And reading a lot of papers. <a href="https://paperswithcode.com/">Papers With Code</a> is a great resource. Note that there are specialized sub-fields like computer vision which do a lot more than throw a convolutional neural network at an image. </li>

<li>Reinforcement Learning: this is even more specialized but it's a fast growing, intellectually rich field. Again, this involves essentially reading and understanding (and implementing) lots of papers, identifying sub-threads that one finds interesting and applying them or extending them. It's generally more mathematical than deep learning. A (non-exhaustive) list of books/resources is:

<ul>
<li><a href="http://www.incompleteideas.net/book/the-book-2nd.html">Reinforcement Learning</a> by Sutton and Barto</li>

<li>A great online <a href="https://rail.eecs.berkeley.edu/deeprlcourse-fa20/">course</a> by Sergey Levine at Berkeley</li>

<li>A <a href="https://sites.google.com/view/berkeley-cs294-190-fa21">collection</a> of papers by Pieter Abbeel </li>

<li> NeurIPS 2021 <a href="https://sites.google.com/view/deep-rl-workshop-neurips2021">Workshop</a> </li> </ul>
</li>


<li> Graphical Models: Another interesting sub-field is that of probabilistic graphical models. Some resources here are:

<ul>
<li>Statistical Rethinking: This is a great (R-based) <a href="https://xcelab.net/rm/statistical-rethinking/">book</a></li>

<li>Pyro: A PyTorch-based <a href="https://pyro.ai/">library for graphical models</a></li></ul></li></ul>

<p>In general, to give a sense of how specialized things can get, there's the sub-field of optimal statistical decision making (related to reinforcement learning). See: <a href="https://www.amazon.com/Optimal-Statistical-Decisions-Morris-DeGroot/dp/047168029X">Optimal Statistical Decisions by  DeGroot</a> or <a href="https://tor-lattimore.com/downloads/book/book.pdf">Bandits by Lattimore and Szepesv&aacute;ri</a> or <a href="https://rltheorybook.github.io">Reinforcement Learning: Theory and Algorithms by Agarwal, Jiang, Kakade, Sun</a>. </p></ul></li>

<li> <p>Lastly, a philosophical point: there are two extreme viewpoints. One is to know which tool to use, pick up a pre-implemented version online and apply it to one's problem. This is a very reasonable approach for most practical problems. The other is to deeply understand how and why something works. This approach takes much more time but gives one the advantage of modifying/extending the tool to make it more powerful. </p>

<p>The problem with the first approach is that when something doesn't work, it's easy to give up since one doesn't understand the internals. The problem with the second approach is that it generally is much more time-consuming (maybe that's not a problem) and must be accompanied by application to problems (practical or not) otherwise it's easy to sit in a theoretical void.</p>

<p>My very opinionated advice is to do both. Always apply the techniques to problems. The problems can be artificial where you generate the dataset or they can be real problems. See where they fail and where they succeed. But, also don't ignore the math and the fundamentals. The goal is also to understand and not just use. The understanding almost always has some mathematical elements. Initially, it might seem like a foreign language but eventually it lets one generate new ideas and see connections that are just hard to see otherwise. Sometimes the mathematics can seem gratuitous but even then, it is a post-hoc justification which suggests new extensions and new experiments to do. </p></li>

</ol>

Good luck!
</body>

</html>