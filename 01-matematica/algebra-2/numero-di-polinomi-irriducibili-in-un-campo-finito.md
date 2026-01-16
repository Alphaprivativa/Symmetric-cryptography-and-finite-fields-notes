---
aliases:
- Spezzamento di irriducibili su campi finiti
- Splitting field of irreducibiles over finite fields
---


# Numero di polinomi irriducibili in un campo finito

## Prodotto di irriducibili

> Siano
> - $\mathbb K$ un [[Campo]] ==finito==
> - $q:= |K|$, cioè $\mathbb K=\mathbb F_q$
> 
> Allora
> $$f=x^{q^n}-x = \prod g_i$$
> dove gli $g_i$ sono tutti i polinomi monici [[Riducibile|Irriducibili]] di grado $d \mid n$ senza ripetizioni.
> 
> 
>>[!dim]- #### Dimostrazione
>> - Ogni fattore irriducibile di $f$ ha [[Polinomi a coefficienti in un campo#Molteplicità delle radici e derivata|molteplicità]] $1$ perché
>>   $$MCD(f,f')=1$$
>> - Sia $g$ ==irriducibile== di grado $d \mid n$ :
>>   - Osservo che
>>     $$\mathbb K[\alpha]\cong \mathbb K[x]/(g)\cong \mathbb F_{q^d }$$
>>   - Osservo che il [[Campo di spezzamento]] di $f$ è $\mathbb F_{q^n }$ e ogni elemento di questo campo è radice del polinomio $f$
>>   - Osservo che per il [[Teorema di Classificazione dei sottocampi di un campo finito]] $\mathbb F_{q^d }\subseteq \mathbb F_{q^n }$
>>   
>>   Allora $\alpha$ è radice fi $g$ e di $f$ contemporaneamente, ma siccome $g$ è irriducibile esso è il [[Polinomio minimo]] di $\alpha$, quinid
>>   $$g \mid f$$
>>
>> - Sia $g$ ==irriducibile== tale che $g \mid f$ :
>>   - Osservo che
>>     $$\mathbb K[\alpha]\cong \mathbb K[x]/(g)\subseteq \mathbb F_{q^n }$$
>>     perché $\mathbb F_{q^n }$ è campo si spezzamento per $f$
>>   
>>   Allora per il [[Lemma della torre]] $q^{\deg g}:=[\mathbb K[\alpha]: \mathbb K]\mid [\mathbb F_{q^n }: \mathbb K]= q^n$ per cui $\deg g \mid n$
>
>
> > [!cor] ### Corollario (Spezzamento di irriducibili su campi finiti)
> > 
> > Siano
> > - $\mathbb K$ un [[Campo]] ==finito==
> > - $q:= |\mathbb K|$, cioè $\mathbb K= \mathbb F_q$
> > - $g \in \mathbb K[x]$ [[Riducibile|Irriducibile]] con $d:=\deg g$
> > 
> > Allora il [[Campo di spezzamento]] di $g$ su $\mathbb K$ è $\mathbb F_{q^d}$
> > 
> > > [!dim]- #### Dimostrazione
> > > Sia $\mathbb L$ il [[Campo di spezzamento]] di $g$ su $\mathbb K$, allora
> > > - $\mathbb F_{q^d}\subseteq \mathbb L:$ basta osservare che se $\alpha$ è radice di $g$
> > >   $$\mathbb L \supseteq \mathbb K[\alpha]=\mathbb K[x]/(g)=\mathbb F_{q^d}$$
> > > - $\mathbb L \subseteq \mathbb F_{q^d}:$ Sappiamo dal ==teorema di cui sopra== che $g \mid f:= x^{q^d}-x$, allora il campo di spezzamento di $g$ sta nel campo di spezzamento di $f$

## Numero di irriducibili

> ### By degree
> Siano
> - $\mathbb K$ un [[Campo]] ==finito==
> - $q:=|\mathbb K|$
> 
> Costruisco
> $$\begin{align}\varphi: \mathbb Z &\longrightarrow \mathbb Z\\ d& \longmapsto \#\{\text{polinomi irriducibili monici di grado } d \text{ in } \mathbb K\}\end{align}$$
> Allora
> $$q^n= \sum\limits_{d \mid n} d\cdot\varphi(d)$$
>
>>[!note] Nota
>> Esiste una formula chiusa per $\varphi$ che si ottiene considerando l'anello di convoluzione di Dirichlet.
>> Infatti sia $\mu$ l'inversa della funzione $\mathbb N\ni n \overset{\mathscr i}\longmapsto 1\in \mathbb N$ nell'anello di convoluzione, cioè
>> $$\mu(n)= \begin{cases} 1 & \text{se } n=1\\ (-1)^r & \text{se } n = p_1\cdots p_r\text{ con } p_i \text{ primi distinti}\\ 0&\text{altrimenti} \end{cases}$$
>> Allora
>> $$\varphi(n)=  \dfrac{1}{n}\sum\limits_{d \mid n} \mu(d)q^{n/d}$$
>
>>[!dim]- #### Dimostrazione
>> - (Non dimostriamo la nota)
>> 
>> dal Teorema precedente sappiamo che se $\{g_{d,i}\}_{i=1,\ldots,\varphi(d)}$ è l'insieme degli irriducibili di grado $d$ su $\mathbb K$
>> $$f=x^{q^n }-x= \prod_{\begin{matrix}d \mid n\\ i=1,\,\ldots\,, \,\varphi(d)\end{matrix}} g_{d,i}$$
>> Allora
>> $$q^n=\deg f= \deg \prod _{d \mid n} g_{d,i}=\sum\limits_{d \mid n}\sum\limits_{i=1}^{\varphi(d)}\deg g_{d_i}=\sum\limits_{d \mid n} d\cdot\varphi(d)$$

> ### By order
> Sia
> - $\mathbb F_q$ un [[Campo]] ==finito==
> - Sia $f \in \mathbb F_q[x]$ un ==polinomio irriducibile==, allora ne consideriamo l'[[Polynomial order over a finite fields|Ordine]]
>   $$\text{ord}(f):= \min\{r \in \mathbb N: f \mid x^r-1\}$$
> 
> Consideriamo
> $$\begin{align}\psi: \mathbb Z &\longrightarrow \mathbb Z\\e& \longmapsto \#\{\text{Polinomi irriducibili di ordine }e\}\end{align}$$
> 
> Allora
> 1. se $e=\text{ord}(f)$ allora
>    $$\deg f= \text{ord}_{\mathbb Z_e^{\star}}(q)$$
> 2. Vale la seguente formula per $\psi$
> 
> $$\psi(e):= \begin{cases}\dfrac{\phi(e)}{\text{ord}_{\mathbb Z_e^\star}(q)}& \text{se }n\ge 2\\ 2&\text{se } n=1\\0&\text{altrimenti}\end{cases}$$
> 
> > [!dim]- #### Dimostrazione
> > 
> > - ($1)$:  sia $\alpha$ una radice di $f$, allora $e:=\text{ord}(f)=\text{ord}_{\mathbb F_{q^{\deg f}}^\star}(\alpha)$.  Quindi $e \mid q^{\deg f}-1$, ma in particolare $\deg f$ è il minimo $n \in \mathbb N^\star$ tale che $e \mid q^{n}-1$ perchè $\alpha$ vive in $F_q[x]/(f)$ ma in nessun sottocampo sottostante, questo perchè $f$ è irriducibile, questo perchè $F_{q^{\deg f}}$ è il campo di spezzamento di $f$, quindi aggiungere una radice vuol dire aggiungerle tutte.
> >    Allora $\deg f$ è il minimo per cui $q^n=1\mod e$ cioè
> >    $$\deg f= \text{ord}_{\mathbb Z_e^\star}(q)$$
> > - $(2):$ Sia $C(n)$ l'$n$-esimo polinomio ciclotomico, quindi chiaramente $f \mid C(e)$ perché le sue radici sono tutte di ordine $e$. D'altronde sappiamoc he $\deg f= \text{ord}_{\mathbb Z_e^\star}(q)$, quinid in tutto abbiamo
> >   $$\dfrac{\phi(e)}{\text{ord}_{\mathbb Z_e^\star}(q)}\text{ polinomi monici irriducibili di ordine } e$$ 

^05e4fe
