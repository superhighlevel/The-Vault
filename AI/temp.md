$$\frac{\partial C}{\partial \hat{y_i}} = \frac{\partial}{\partial \hat{y_i}} \frac{1}{N} \sum_{i=1}^N (y_i - \hat{y_i})^2 = 2 \times \frac{1}{N}\sum_{i=1}^N(y_i - \hat{y_i})$$
$$\frac{\partial \hat{y}}{\partial z}  = \frac{\partial}{\partial z}\sigma(z) = \frac{\partial}{\partial z}(\frac{1}{1+e^{-z}}) = \frac{e_{-z}}{(1+e^{-z})^2} = (\frac{1}{1+e^{-z}})\times(\frac{e^{-z}}{1+e^{-z}}) = (\frac{1}{1+e^{-z}}) \times(1 - (\frac{1}{1+e^{-z}})) = \sigma(z)\times (1-\sigma(z))
$$
$$\frac{\partial z}{\partial w_i} = \frac{\partial}{\partial w_i}(z) = \frac{\partial}{\partial w_i} \sum_{i=1}^N(x_iw_i+b_i) = x_i$$

$$\frac{\partial z}{\partial b} = \frac{\partial}{\partial b}(z) = \frac{\partial}{\partial b} \sum_{i=1}^N(x_iw_i+b) = 1$$

$$(6) \Leftrightarrow \frac{\partial C}{\partial w_i}=\frac{2}{N}\times\sum_{i=1}^N(y_i - \hat{y}) \times \sigma(z) \times (1 - \sigma(z)) \times x_i$$

$$\frac{\partial C}{\partial b} = \frac{\partial C}{\partial \hat{y}} \times \frac{\partial \hat{y}}{\partial z} \times \frac{\partial z}{\partial b}=\frac{2}{N}\times\sum_{i=1}^N(y_i - \hat{y}) \times \sigma(z) \times (1 - \sigma(z)) $$

$$w_i = w_i - (\alpha \times \frac{\partial C}{\partial w_i})$$
$$b = b -(\alpha \times \frac{\partial C}{\partial b})$$

$$k(x,y) \bigstar f(x,y) = \sum_{u=0}^{m}\sum_{v=0}^{n}k(u, v)f(x-u, y-v)$$
$$y_{11} = x_{11}.k_{11} + x_{12}.k_{12} + x_{13}.k_{13} + x_{21}.k_{21} + x_{22}.k_{22} + x_{23}.k_{23} + x_{31}.k_{31} + x_{32}.k_{32} + x_{33}.k_{33}$$

$$y_{12} = x_{12}.k_{12} + x_{13}.k_{13} + x_{14}.k_{14} + x_{22}.k_{22} + x_{23}.k_{23} + x_{24}.k_{24} + x_{32}.k_{32} + x_{33}.k_{33} + x_{34}.k_{34}$$

$$L_{cross\_entrophy}(X_t,X_g) = -\sum_ix_{t_i}log(x_{g_i})$$
$$\underset{D}{max}V(D) = \mathbb{E}_{x\sim p_{data}(x)}[logD(x)] + \mathbb{E}_{x\sim p_{z}(z)}[log(1 - D(G(z)))]$$
$$maxV(G) = \mathbb{E}_{z\sim p_z(z)}[long(1 - D(G(z)))]$$

$$minmaxV(D, G)=\mathbb{E}_{z\sim p_{data}(x)}[logD(x)] + \mathbb{E}_{z \sim{p_z}(z)}[log(1 -D(G(z)))]
$$

$$\nabla$$

$$z \sim \mathcal{N}(0,1)\ or\ z\sim \mathcal{U}(-1, 1)
$$

$$\nabla_{\theta_d}\frac{1}{m} \sum_{i=1}^m [logD(x^{(i)}) + log(1 - D(G(z^{i})))]
$$

