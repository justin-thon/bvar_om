bmr
* Normal-inverse-Wishart Prior
* Minnesota Prior
  * (Koop and Korobilis, 2010, p. 7) version
  * (Canova, 2007, p. 378) version
    * harmonic decay d(l)=l^{H_4}
    * geometric decay d(l)=H_4^{1-l}
* steady state prior


Eviews:
* Litterman/Minnesota prior. (koop korobilis version) v
* Normal-Wishart prior. v
* Sims-Zha Normal-Wishart prior.
* Sims-Zha Normal-flat. v
* Diffuse prior 
? conjugate Normal-Wishart 


http://www.ihs.ac.at/vienna/resources/Economics/Papers/20120426_Slides_Giannone.pdf
* Minnesota prior (Litterman, 1980 and 1986) 
* Inverse-Wishart prior on \Sigma
* Sum-of-coefficients prior (Doan, Litterman and Sims 1984) 
* Single-unit-root prior (Sims, 1993)

http://personal.strath.ac.uk/gary.koop/kk3.pdf
Gary Koop (from bvar_full)
* Diffuse (Jeffreys) (MC integration)
* Minnesota (MC integration)
* Normal-Wishart (MC integration)
* Independent Normal-Wishart (Gibbs)
* SSVS in mean - Wishart (Gibbs)
* SSVS in mean - SSVS in in covariance (Gibbs)
SSVS -- Stochastic Search Variable Selection

y_t=a_0+A_1 y_{t-1} + \varepsilon_t


http://www.ecb.europa.eu/events/pdf/conferences/schorfheide.pdf
* Priors from General Equilibrium Models for VARs

Обозначения:
y_t=\Phi_0+\Phi_1 y_{t-1} +u_t



msbvar:

szbvar:
* Sims-Zha Normal-Wishart prior
* Sims-Zha Normal-flat prior
* (?) flat-flat prior

szbsvar
* "model described by Sims and Zha (1998) and Waggoner and Zha (2003)"


уже начатая статья
y_t=v+A_1 y_{t-1} + \ldots + u_t





Sims, C.A. and Tao A. Zha. 1998. "Bayesian Methods for Dynamic Multivariate Models." International Economic Review. 39(4):949-968.

Waggoner, Daniel F. and Tao A. Zha. 2003a. "A Gibbs sampler for structural vector autoregressions" Journal of Economic Dynamics \& Control. 28:349–366.

Waggoner, Daniel F. and Tao A. Zha. 2003b. "Likelihood preserving normalization in multiple equation models". Journal of Econometrics. 114: 329–347.

Brandt, Patrick T. and John R. Freeman. 2006. "Advances in Bayesian Time Series Modeling and the Study of Politics: Theory Testing, Forecasting, and Policy Analysis". Political Analysis 14(1):1-36.


Протокол:

1.       Сезонная корректировка
2.       Взятие логарифмов для всех переменных, исключая те, что выражены  в процентах.
3.       Проверка на стационарность для определения априорного  матожидания (опционально. Carriero этого вообще не делает) 
4. Формируем выборки с 3, 5, 7, 15 и 23 переменными 
5. Оценивать нужно RW, VAR(3)=BVAR(\lambda=\infty), VAR(5), BVAR_ Minnesota, сопр. N-IW
6.  Количество лагов для  BVAR выбираем путем максимизации marginal density. Лаги смотрим от 1 до 12. Первая точка в обучающей выборке – январь 1996, количество исходных наблюдений – 150, выборка не меняется с изменением числа лагов. Второй вариант – количество исходных наблюдений – 200. Из любопытства можно сравнить выбранное предпочитаемое количество лагов с результатом минимизации информационных критериев.  
7.  Подсчет \lambda по банбуровской схеме.  Процентную ставку во внимание не принимаем (хотя, как мы выяснили, она не вредная, но и не полезная)
8 Подсчет \lambda_1 путем максимизации marginal density. Можно по отдельности, можно максимизировать одновременно по \lambda_1 и по p.  \lambda_2  надо ставить равным 1. А по \lambda_3 и, возможно,  \lambda_4 можно оптимизировать. Вопрос, хватает ли для этого данных? 
9. Прогнозы строим на 1,3, 6, 9 и 12 месяцев. Считаем темп роста прогнозируемых переменных (можно начать с прироста IP   и инфляции, потом, если результаты будут приятными, можно расширить число прогнозируемых переменных). 
10. Сдвигаем наблюдения на единицу и делаем то же, что в п. 9. Количество наблюдений в выборке всегда 150. Последнее прогнозируемое наблюдение – апрель 2015, количество прогнозов на 1 период будет больше, чем на 3, а прогнозов на 3 будет больше, чем на 6
11. Считаем MSFE по всем прогнозам, делаем выводы. 
12.  Потом решаем, что были глубоко неправы везде, где можно. Возвращаемся и переделываем. 






