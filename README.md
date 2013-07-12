MixtureModels.jl
================

Gaussian mixture models in Julia:

	using MixtureModels
	using Vega

	mu = [0.0 25.0; 0.0 25.0]
	sigma = Array(Float64, 2, 2, 2)
	sigma[:, :, 1] = [1.0 0.9; 0.9 1.0]
	sigma[:, :, 2] = 7.5 * [1.0 0.0; 0.0 1.0]
	p = [0.9, 0.1]

	distr = MixtureMultivariateNormals(mu, sigma, p)

	X = rand(distr, 10_000)

	scatterplot(x = X'[:, 1], y = X'[:, 2])
