<h1 align="center">
  specgp
</h1>
<p align="center">
    <a href='https://specgp.readthedocs.io/en/latest/?badge=latest'>
        <img src='https://readthedocs.org/projects/specgp/badge/?version=latest' alt='Documentation Status' /></a>
    <a href="https://travis-ci.com/github/tagordon/specgp">
        <img src="https://travis-ci.com/tagordon/specgp.svg?branch=master"></a>
    <a href="https://github.com/tagordon/specgp/blob/master/LICENSE">
        <img src="https://img.shields.io/badge/license-MIT-blue.svg?style=flat"></a>
    <a href="https://arxiv.org/abs/2007.05799">
        <img src="https://img.shields.io/badge/arXiv-2007.05799-b31b1b.svg?style=flat"></a>
    </br>
    <a href="https://github.com/exoplanet-dev/exoplanet">
        <img src="https://img.shields.io/badge/powered_by-exoplanet-FE4365.svg?style=flat"></a>
    <a href="https://github.com/dfm/celerite">
        <img src="https://img.shields.io/badge/powered_by-celerite-FE4365.svg?style=flat"></a>
    <a href="https://github.com/pymc-devs/pymc3">
        <img src="https://img.shields.io/badge/powered_by-pymc3-FE4365.svg?style=flat"></a>
</p>
<p>
    <em>specgp</em> enables 2D Gaussian process computations in <a href="https://github.com/exoplanet-dev/exoplanet.git"><em>exoplanet</em></a>. This is accomplished by a new kernel term which combines 
    a <em>celerite</em> term with a specification of the covariance for the second dimension. The 
    method     
</p>

<h2 align="center">
    installation
</h2>
<p>
    Installation is via pip:
    </br>
    <code>pip install specgp</code>
</p>
<h2 align="center">
    documentation
</h2>
<p>
    Documentation for <em>specgp</em> is available <a href="https://specgp.readthedocs.io">here</a>.
</p>
<h2 align="center">
    example
</h2>
<p>
    One straightforward application of *specgp* is modeling multiwavelength 
    stellar variability. While the tutorials at 
    <a href="https://specgp.readthedocs.io">specgp.readthedocs.io</a> cover 
    the details of optimizing a GP model and running MCMC on this kind 
    of data, here we present a simple demonstration of a multiwavelength 
    variability model that illustrates the most basic usage of *specgp*:
    
    We start by defining the covariance in the time dimension 
    using a *celerite* term:
    
    ```python
    import numpy as np
    import exoplanet as xo

    term = xo.gp.terms.SHOTerm(log_S0=0.0, log_w0=1.0, log_Q=-np.log(np.sqrt(2)))
    ```
</p>