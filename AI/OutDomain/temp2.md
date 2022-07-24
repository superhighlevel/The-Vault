$$- \nabla_{\theta_g} \frac{1}{m} \sum_ {i=1}^m log(1 - D(G(z^{(i)})))\ or \ \nabla_{\theta_g} \frac{1}{m}\sum_ {i=1}^m log(D(G(z^{(i)})))
$$

$$log(1 - D(G(z^{(i)})))$$



$$L^{SR} = l^{SR}_X + 10^{-3}l_{Gen}^{SR}$$

$$ls^{SR}_{VGG/i.j} = \frac{1}{W_{i,j}H_{i,j}} \sum_{x=1}^{W_{i,j}}\sum_{y=1}^{H_{i,j}}(\phi_{i,j}(I^{HR})_{x,y}-\phi_{i,j}(G_{\theta_G}(I^{HR}))_{x,y})^2
$$

$$L_{total} = \uplambda_pL_{pixel} + \uplambda_{d}L_{disc} + \uplambda_{f}L_{feature} + \uplambda_{s}L_{smooth} 
$$



$$SSIM(x, y) = \frac{(2\mu_x\mu_y+c_1)(2\sigma_{xy}+c_2)}{(\mu_x^2+\mu_y^2+c_1)(\sigma_x^2+\sigma_y^2+c2)}
$$


$$\mathcal{G}:L\rightarrow (a,b)$$
$I = (L,a,b)$
Gọi biến $\theta$ và $w$ lần lượt là các hệ số của trình sinh $\mathcal{G_{\theta}}$ trình so sánh $D_{w}$. Quá trình huấn luyện được diễn ra trên tập hình ảnh màu thật. Trong đó với mỗi bức ảnh màu ta có $I_r=(L, a_r, b_r)$ trong hệ màu Lab. Ta sẽ cho mô hình học cách tô màu bằng cách tách tập huấn huấn luyện ra thành hai phần: Ảnh đen trắng $L$ và 2 kênh sắc độ $(a_r, b_r)$.
Đồng thời $\mathcal{G_\theta}$ không chỉ học cách để tô màu mà còn là một vector phấn bố của các lớp, ký hiệu là $y \in \mathbb{R}^m$, với $m$ là số lớp cố định. Việc này sẽ giúp cung cấp thông tinh về tỉ lệ phân bố của các lớp chứa ngữ cảnh của và vật thể có mặt trong hình ảnh. Vì thế Trình sinh sẽ chưa 2 mô hình con khác biệt nhau trong đó. Điều này được ký hiệu bằng $\mathcal{G}_{\theta} = (\mathcal{G}_{\theta_1}^1, \mathcal{G}_{\theta_2}^2)$, với $\theta = (\theta_1 , \theta_2)$ đại hiện cho tất cả các trọng số của mô hình, $\mathcal{G}_{\theta_1}^1:L\rightarrow (a,b)$ và $\mathcal{G}_{\theta_1}^1:L\rightarrow y$ 

$$\mathcal{L}(\mathcal{G}_{\theta}, D_w) = \mathcal{L}_e(\mathcal{G}_{\theta_1}^1) + \lambda_g\mathcal{L}_e(\mathcal{G}_{\theta_1}^1, D_w) + \lambda_s\mathcal{L}_s(\mathcal{G}_{\theta_2}^2)
$$

Thuật ngữ đầu tiên biểu thị hàm lỗi màu - color error loss.
$$\mathcal{L}_e(\mathcal{G}_{\theta_1}^1) = \mathbb{E}_{(L, a_r, b_r)\sim \mathbb{P}_r}[||\mathcal{G}_{\theta_1}^1(L) - (a_r, b_r)||_2^2$$
trong đó $\mathbb{P}_r$ là phân phối giữa các hình ảnh màu thật và $||.||^2_2$ được hiểu là chuẩn Euclide. Lưu ý rằng khoảng cách Euclide trong không gian màu Lab thích nghi hơn với sắc quan hơn. 
Tiếp theo, 
$$\mathcal{L}_s(\mathcal{G}_{\theta_2}^2) = \mathbb{E}_{L\sim \mathbb{P}_{rg}}[KL(y_v||\mathcal{G}_{\theta_2}^2))]$$
là ký hiệu toán hàm mất mát phân phôi của các lớp - class distribution loss, với $\mathbb{P}_{rg}$ là phân phối của hình ảnh đen trắng đầu vào, và $y_v \in \mathbb{R}^m$ là vector phân phối đầu ra của mô hình VGG-16 áp dụng cho hình ảnh đen trắng. $.||.$ đại diện cho phân kỳ Kullback–Leibler. 
Cuối cùng, $\mathcal{L}_g$ là ký hiệu của WGAN loss thay vì là GAN loss truyền thống. WGAN - Wasserstein GAN loss mang nhiều đặc điểm nổi trội hơn như là tránh được Vanishing Gradients và gọn hơn, kèm theo đó là sự ổn định trong quá trình huấn luyện. Để tính giá trị này, mô hình sẽ sử dụng đối ngẫu Kantorovich-Rubinstein.  Với $D_w \in \mathcal{D}$ , với $\mathcal{D}$ đại diện cho tập của hàm 1-Lipschitz. Tóm gọn lại ta có WGAN loss được biểu diễn như sau:
$$\mathcal{L}_g(\mathcal{G}_{\theta _1}^1, D_w) = \mathbb{E}_{\tilde{I}\sim \mathbb{P}_r}[D_w(\tilde{I})] - \mathbb{E}_{(a,b)\sim\mathbb{P}_{\mathcal{G}_{\theta _1}^1}}[D_w(L,a,b)] - \mathbb{E}_{\hat{I}\sim\mathbb{P}_{\hat{I}}}[(||\nabla_{\hat{I}}D_w(\hat{I})||_2-1)^2]$$
với $\mathbb{P}_{\mathcal{G}_{\theta _1}^1}$ là phân phối từ mô hình của $\mathcal{G}_{\theta _1}^1(L)$, với $L \sim \mathbb{P}_{rg}$.  $\mathbb{P}_{\hat{I}}$  được ngầm định là lấy mẫu thống nhất dựa theo các đường thẳng giữa các cặp điểm được lấy mẫu từ phân phối dữ liệu $\mathbb{P}_r$ và phân phối của Trình sinh $\mathbb{P}_{\mathcal{G}_{\theta _1}^1}$. Khi tối ưu hóa liên quan đến các tham số phân biệt, thuật toán của mô hình tối thiểu hóa giá trị của hàm mất mát thay vì tối đa hóa. 
Từ các hàm mất mát trên, ta sẽ đi tìm trọng số của $\mathcal{G_{\theta}}, D_w$ bằng cách giải bài toán min-max: $$\underset{\mathcal{G}_{\theta}}{min}\ \underset{D_w}{max}\ \mathcal{L}(\mathcal{G_{\theta}}, D_w)$$
Các trọng số $\lambda_g, \lambda_s$ được gán cứng giá trị lần lượt là 0.1 và 0.003.

$$MSE = \frac{\sum_{m=1, n=1}^{M,N}[I_1(m,n)]-I_2(m,n)}{M*N}$$
$$PSNR = 10\ log_{10}(\frac{R^2}{MSE})$$

$$x_t = x_{t-1} + \frac{\epsilon}{2}\nabla_xp(x_{t-1})+\sqrt{\epsilon}z_t \ \ \ where z_t \sim \mathcal{N}(0, I)$$



$T \rightarrow \infty, \epsilon \rightarrow 0, x_t$ bằng phân phối chuẩn $p(x)$





