##R programmed functions to the model by Carranza and Polo (2015, R.Soc.open.Sci.) on the evolution of sexual reproduction.
####V. Polo, J.G. Rubalcaba and J. Carranza

Carranza and Polo (2015). Sexual reproduction with variable mating systems can resist asexuallity in a rock-paper-scissors dynamics. Royal Society Open Science:http://dx.doi.org/10.1098/rsos.140383.


####Summary from Carranza & Polo (under review)
While sex can be advantageous for a lineage in the long term, we still lack an explanation for its maintenance with the twofold cost per generation. Here we model an infinite diploid population where two autosomal loci determine, respectively, the reproductive mode, sexual vs. asexual, and the mating system, polygynous (costly sex) vs. monogamous (assuming equal contribution of parents to offspring, i. e. non-costly sex). We show that alleles for costly sex can spread when non-costly sexual modes buffer the interaction between asexual and costly sexual strategies, even without twofold benefit of recombination with respect to asexuality. The three interacting strategies have intransitive fitness relationships leading to a rock-paper-scissors dynamics, so that alleles for costly sex cannot be eliminated by asexuals in most situations throughout the parameter space. Our results indicate that sexual lineages with variable mating systems can resist the invasion of asexuals and allow for long-term effects to accumulate, thus providing a solution to the persisting theoretical question of why sex was not displaced by asexuality along evolution.


#### How to use

The function programed in R allows generating the evolutionary dynamics of alleles determining 
(1) asexual (allele a in locus S) vs. sexual reproduction (allele s in locus S) and, in the second case, (2) non-costly sexual reproduction (allele n in locus M) vs. costly sexual reproduction (alle c in locus M).


###### (1) Copy-paste and execute the function's code in R.

###### (2) Specify function parameters (see definition of parameters and example below) and store the output as an object: 

###### Parameter Meaning 

 m = Maximum potential number of mates for a polygynous male

 R = Benefit of recombination with respect to asexuality 

 b = Proportion of male parental contribution accepted by nn female

 k = Dominance effect of allele c in locus M 

 alpha = Probability of as individual choosing asexual strategy

 a0 = Initial frequency of allele a (i.e., asexuality) in locus S

 n0 = Initial frequency of allele n (i.e., non-costly sexuality) in locus M

 gen = number of generations

###### Output

The function generates a matrix containing as many rows as generations (gen) and 9 columns. Each colum represent the dynamics of the variables necesary to estimate allele frequencies (see below). The last 4 columns are the allele frequencies of alleles a and s (locus S), n and c (locus M) respectively.

 1 - pi: Mean number of mates of homozygote nn males in the population 

 theta: Mean number of mates of heterozygote cn males in the population

 1 + phi: Mean number of mates mate for polygynous cc males in the population 

 tao: Proportion on sexual individuals in the population 

 a: Allele at locus S influencing asexuality 

 s: Allele at locus S influencing sexuality 

 n: Allele at locus M influencing non-costly sex 

 c: Allele at locus M influencing costly sex 


output <- CarranzaandPolo(m = 3.3, R = 1.6, b = 0.5, k = 0.5, alpha = 0.5, a0 = 0.99, n0 = 0.99, gen = 10000)

###### (3) Plot the dynamic of allele frequencies and the dynamic attractor using:

plot(output$a, ylim = c(0,1), type = "l", col = "red")

lines(output$c, col = "blue")

plot(c ~ a, output, type = "l")




