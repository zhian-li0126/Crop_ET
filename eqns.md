| Physics          | Governing Equation                                                                                                                                                              | Variable                   | Initial Condition             | Boundary Condition                                                                                   |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------- | ----------------------------- | ---------------------------------------------------------------------------------------------------- |
| Momentum balance | $$\rho\left(\frac{\partial \mathbf{u}}{\partial t}+\mathbf{u}\cdot\nabla\mathbf{u}\right)=-\nabla p+\mu\nabla^2\mathbf{u}+\rho\mathbf{g}$$ <br><br> $$\nabla\cdot\mathbf{u}=0$$ | Air velocity $(\mathbf{u})$ <br>Pressure ($p$) | $$\mathbf{u}(x,y,z,0)=0$$ $$p(x,y,z,0)=p_{\text{atm}}$$   | **Inlet:** $$\mathbf{u}=\mathbf{u}_{in}$$ <br><br> **Walls, LED, lettuce surface (No-slip Condition):** $$\mathbf{u}=0$$ **Outlet:** $$p=p_{out}= 0 \text{Pa}$$ |

<br>
<br>


### Air Domain

| Physics | Governing Equation | Variable | Initial Condition | Boundary Condition |
|---|---|---|---|---|
| Energy balance <br> **In air domain** | $$\rho_a C_{p,a}\left(\frac{\partial T_a}{\partial t}+\mathbf{u}\cdot\nabla T_a\right)=\nabla\cdot(k_a\nabla T_a)+Q_a$$ | Air temperature, $$T_a$$ | $$T_a(x,y,z,0)=T_{a,0}$$ | **Inlet:** $$T_a=T_{in}$$ <br><br> **Outlet:** zero-gradient / convective outflow <br> $$-\mathbf{n}\cdot(k_a\nabla T_a)=0$$ <br><br> **Chamber walls:** insulated wall <br> $$-\mathbf{n}\cdot(k_a\nabla T_a)=0$$ <br><br> or convective heat loss: <br> $$-\mathbf{n}\cdot(k_a\nabla T_a)=h_{\text{wall}}(T_a-T_{\infty})$$ |
| Energy balance <br> **LED heat source** | $$q_{\text{LED}}=\frac{\eta_hP_{\text{LED}}}{A_{\text{LED}}}$$ | LED heat flux, $$q_{\text{LED}}$$ | $$q_{\text{LED}}(t=0)=q_{\text{LED},0}$$ | **LED surface:** prescribed heat flux <br> $$-\mathbf{n}\cdot(k_a\nabla T_a)=q_{\text{LED}}$$ |

### Lettuce Domain

| Physics | Governing Equation | Variable | Initial Condition | Boundary Condition |
|---|---|---|---|---|
| Energy balance <br> **In lettuce domain** | $$\rho_l C_{p,l}\frac{\partial T_l}{\partial t}=\nabla\cdot(k_l\nabla T_l)+Q_l$$ | Lettuce temperature, $$T_l$$ <br><br> Heat from respiration $$Q_l$$ | $$T_l(x,y,z,0)=T_{l,0}$$ <br><br> Common assumption: <br> $$T_{l,0}=T_{a,0}$$ | **Lettuce-air interface:** heat exchange between lettuce and surrounding air <br> $$-\mathbf{n}\cdot(k_l\nabla T_l)=H+\lambda E$$ <br><br> where <br> $$H=h_c(T_l-T_a)$$ |
| Lettuce surface energy balance <br> **Leaf-air interface** | $$\lambda E+H=\pi R_{\gamma}+Q_h-G-K_s(T_l-T_a)$$ | Sensible heat flux, $$H$$ <br><br> Latent heat flux, $$\lambda E$$ | $$T_l(t=0)=T_{l,0}$$ <br><br> $$E(t=0)=E_0$$ | **Lettuce surface:** transpiration vapor flux coupled to mass transfer <br> $$-\mathbf{n}\cdot(D_v\nabla c_v)=E$$ <br><br> **Heat flux to air:** <br> $$-\mathbf{n}\cdot(k_a\nabla T_a)=H+\lambda E$$ |




<br>
<br>

| Physics      | Governing Equation                                                                           | Variable                         | Initial Condition                                                                                | Boundary Condition                                                                                                                                                                                                                                 |
| ------------ | -------------------------------------------------------------------------------------------- | -------------------------------- | ------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Mass balance | $$\frac{\partial c_v}{\partial t}+\mathbf{u}\cdot\nabla c_v=\nabla\cdot(D_v\nabla c_v)+S_v$$ | Water vapor concentration, ${(c_v)}$ | $$c_v(x,y,z,0)=c_{v,0}$$ <br><br>  | **Inlet:** $$c_v=c_{v,in}$$ <br><br> **Outlet:** $$-\mathbf{n}\cdot\nabla c_v=0$$ <br><br> **Walls and LED:** $$-\mathbf{n}\cdot(D_v\nabla c_v)=0$$ <br><br> **Lettuce surface:** $$-\mathbf{n}\cdot(D_v\nabla c_v)=\mathbf{E}$$                                                                                                                             |
