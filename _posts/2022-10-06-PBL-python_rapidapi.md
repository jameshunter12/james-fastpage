---
keywords: fastai
description: APIs can be found all over the internet.  A great consolidator of many APIs is <mark>RapidAPI</mark>.  In this blog we will use a site to consolidates API stats.  Learning a few lines of code and you can start extracting lots of data from the internet via APIs.  
title: Python RapidAPI
toc: true
image: /images/rapidapi.png
permalink: /techtalk/rapidapi
categories: [1.A, 5.B, 5.D]
tags: [api, rapidapi]
type: pbl
week: 7
nb_path: _notebooks/2022-10-06-PBL-python_rapidapi.ipynb
layout: notebook
---

<!--
#################################################
### THIS FILE WAS AUTOGENERATED! DO NOT EDIT! ###
#################################################
# file to edit: _notebooks/2022-10-06-PBL-python_rapidapi.ipynb
-->

<div class="container" id="notebook-container">
        
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Python,-RapidAPI-Terms">Python, RapidAPI Terms<a class="anchor-link" href="#Python,-RapidAPI-Terms"> </a></h3><blockquote><p>APIs and tooling like Jupyter docs allows many opportunities in fields like Data Science.  As more and more developers use APIs, they build standards in how you setup a client, send requests and receive information...</p>
</blockquote>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Covid19-RapidAPI-Example">Covid19 RapidAPI Example<a class="anchor-link" href="#Covid19-RapidAPI-Example"> </a></h3><blockquote><p>To begin the API journey.  You need to find an API provider.</p>
</blockquote>
<ul>
<li>RapidAPI is a great option.  You must setup and account, but there are many free options.</li>
<li>Goto this page for starters, the <a href="https://rapidapi.com/spamakashrajtech/api/corona-virus-world-and-india-data/">Corona virus World and India data</a>- Under Code Snippets pick Python - Requests</li>
</ul>
<p>RapidAPI, you will select Python Requests type of code to work with you Notebook.</p>
<ul>
<li>The url is the endpoint to which the API is directed</li>
<li>The headers is a dictionary data structure to send special messaging to the endpoint </li>
<li>The requests.request() python function is used to send a request and retrieve their responses</li>
<li>The response variable receives result of of the request in JSON text</li>
</ul>
<p>Next step, is to format the response according to your data science needs</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="sd">&quot;&quot;&quot;</span>
<span class="sd">Requests is a HTTP library for the Python programming language. </span>
<span class="sd">The goal of the project is to make HTTP requests simpler and more human-friendly. </span>
<span class="sd">&quot;&quot;&quot;</span>
<span class="kn">import</span> <span class="nn">requests</span>

<span class="sd">&quot;&quot;&quot;</span>
<span class="sd">RapidAPI is the world&#39;s largest API Marketplace. </span>
<span class="sd">Developers use Rapid API to discover and connect to thousands of APIs. </span>
<span class="sd">&quot;&quot;&quot;</span>
<span class="n">url</span> <span class="o">=</span> <span class="s2">&quot;https://corona-virus-world-and-india-data.p.rapidapi.com/api&quot;</span>
<span class="n">headers</span> <span class="o">=</span> <span class="p">{</span>
    <span class="s1">&#39;x-rapidapi-key&#39;</span><span class="p">:</span> <span class="s2">&quot;6fa44ed3a2msh483515e3beca32dp153a87jsn04ee72a909e0&quot;</span><span class="p">,</span>
    <span class="s1">&#39;x-rapidapi-host&#39;</span><span class="p">:</span> <span class="s2">&quot;corona-virus-world-and-india-data.p.rapidapi.com&quot;</span>
<span class="p">}</span>

<span class="c1"># Request Covid Data</span>
<span class="n">response</span> <span class="o">=</span> <span class="n">requests</span><span class="o">.</span><span class="n">request</span><span class="p">(</span><span class="s2">&quot;GET&quot;</span><span class="p">,</span> <span class="n">url</span><span class="p">,</span> <span class="n">headers</span><span class="o">=</span><span class="n">headers</span><span class="p">)</span>
<span class="c1"># print(response.text)  # uncomment this line to see raw data</span>

<span class="c1"># print(response.json[])</span>

<span class="c1"># This code looks for &quot;world data&quot;</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">&quot;World Totals&quot;</span><span class="p">)</span>
<span class="n">world</span> <span class="o">=</span> <span class="n">response</span><span class="o">.</span><span class="n">json</span><span class="p">()</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="s1">&#39;world_total&#39;</span><span class="p">)</span>  <span class="c1"># turn response to json() so we can extract &quot;world_total&quot;</span>
<span class="k">for</span> <span class="n">key</span><span class="p">,</span> <span class="n">value</span> <span class="ow">in</span> <span class="n">world</span><span class="o">.</span><span class="n">items</span><span class="p">():</span>  <span class="c1"># this finds key, value pairs in country</span>
    <span class="nb">print</span><span class="p">(</span><span class="n">key</span><span class="p">,</span> <span class="n">value</span><span class="p">)</span>

<span class="nb">print</span><span class="p">()</span>

<span class="c1"># This code looks for USA in &quot;countries_stats&quot;</span>
<span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Country Totals&quot;</span><span class="p">)</span>
<span class="n">countries</span> <span class="o">=</span> <span class="n">response</span><span class="o">.</span><span class="n">json</span><span class="p">()</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="s1">&#39;countries_stat&#39;</span><span class="p">)</span>
<span class="k">for</span> <span class="n">country</span> <span class="ow">in</span> <span class="n">countries</span><span class="p">:</span>  <span class="c1"># countries is a list</span>
    <span class="k">if</span> <span class="n">country</span><span class="p">[</span><span class="s2">&quot;country_name&quot;</span><span class="p">]</span> <span class="o">==</span> <span class="s2">&quot;USA&quot;</span><span class="p">:</span>  <span class="c1"># this filters for USA</span>
        <span class="k">for</span> <span class="n">key</span><span class="p">,</span> <span class="n">value</span> <span class="ow">in</span> <span class="n">country</span><span class="o">.</span><span class="n">items</span><span class="p">():</span>  <span class="c1"># this finds key, value pairs in country</span>
            <span class="nb">print</span><span class="p">(</span><span class="n">key</span><span class="p">,</span> <span class="n">value</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>World Totals
total_cases 509,268,964
new_cases 204,268
total_deaths 6,242,509
new_deaths 630
total_recovered 461,827,849
active_cases 41,198,606
serious_critical 42,510
total_cases_per_1m_population 65,334
deaths_per_1m_population 800.9
statistic_taken_at 2022-04-24 11:18:01

Country Totals
country_name USA
cases 82,649,779
deaths 1,018,316
region 
total_recovered 80,434,925
new_deaths 0
new_cases 0
serious_critical 1,465
active_cases 1,196,538
total_cases_per_1m_population 247,080
deaths_per_1m_population 3,044
total_tests 1,000,275,726
tests_per_1m_population 2,990,303
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Digital-Coin-Example">Digital Coin Example<a class="anchor-link" href="#Digital-Coin-Example"> </a></h3><blockquote><p>This example provides digital coin feedback (ie Bitcoin).  It include popularity, price, symbols, etc.</p>
<ul>
<li>A valid X-RapidAPI-Key is required.  Look in code for link to RapidAPI page</li>
<li>Read all comments in code for further guidance</li>
</ul>
</blockquote>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># RapidAPI page https://rapidapi.com/Coinranking/api/coinranking1/</span>
 
<span class="c1"># Begin Rapid API Code</span>
<span class="kn">import</span> <span class="nn">requests</span>
 
<span class="n">url</span> <span class="o">=</span> <span class="s2">&quot;https://coinranking1.p.rapidapi.com/coins&quot;</span>
<span class="n">querystring</span> <span class="o">=</span> <span class="p">{</span><span class="s2">&quot;referenceCurrencyUuid&quot;</span><span class="p">:</span><span class="s2">&quot;yhjMzLPhuIDl&quot;</span><span class="p">,</span><span class="s2">&quot;timePeriod&quot;</span><span class="p">:</span><span class="s2">&quot;24h&quot;</span><span class="p">,</span><span class="s2">&quot;tiers[0]&quot;</span><span class="p">:</span><span class="s2">&quot;1&quot;</span><span class="p">,</span><span class="s2">&quot;orderBy&quot;</span><span class="p">:</span><span class="s2">&quot;marketCap&quot;</span><span class="p">,</span><span class="s2">&quot;orderDirection&quot;</span><span class="p">:</span><span class="s2">&quot;desc&quot;</span><span class="p">,</span><span class="s2">&quot;limit&quot;</span><span class="p">:</span><span class="s2">&quot;50&quot;</span><span class="p">,</span><span class="s2">&quot;offset&quot;</span><span class="p">:</span><span class="s2">&quot;0&quot;</span><span class="p">}</span>
<span class="n">headers</span> <span class="o">=</span> <span class="p">{</span>
   <span class="s2">&quot;X-RapidAPI-Key&quot;</span><span class="p">:</span> <span class="s2">&quot;6fa44ed3a2msh483515e3beca32dp153a87jsn04ee72a909e0&quot;</span><span class="p">,</span>  <span class="c1"># place your key here</span>
   <span class="s2">&quot;X-RapidAPI-Host&quot;</span><span class="p">:</span> <span class="s2">&quot;coinranking1.p.rapidapi.com&quot;</span>
<span class="p">}</span>
 
<span class="n">response</span> <span class="o">=</span> <span class="n">requests</span><span class="o">.</span><span class="n">request</span><span class="p">(</span><span class="s2">&quot;GET&quot;</span><span class="p">,</span> <span class="n">url</span><span class="p">,</span> <span class="n">headers</span><span class="o">=</span><span class="n">headers</span><span class="p">,</span> <span class="n">params</span><span class="o">=</span><span class="n">querystring</span><span class="p">)</span>
<span class="c1"># End Rapid API Code</span>
<span class="n">json</span> <span class="o">=</span> <span class="n">response</span><span class="o">.</span><span class="n">json</span><span class="p">()</span>  <span class="c1"># convert response to python json object</span>
 
<span class="c1"># Observe data from an API.  This is how data transports over the internet in a &quot;JSON&quot; text form</span>
<span class="c1"># - The JSON &quot;text&quot; is formed in dictionary {} and list [] divisions</span>
<span class="c1"># - To read the result, Data Scientist of  Developer converts JSON into human readable form</span>
<span class="c1"># - Review the first line, look for the keys --  &quot;status&quot; and &quot;data&quot;</span>
 
<span class="k">for</span> <span class="n">coin</span> <span class="ow">in</span> <span class="n">json</span><span class="p">[</span><span class="s2">&quot;data&quot;</span><span class="p">][</span><span class="s2">&quot;coins&quot;</span><span class="p">]:</span> <span class="c1"># json is calling the data</span>
   <span class="nb">print</span> <span class="p">(</span><span class="sa">f</span><span class="s1">&#39;</span><span class="si">{</span><span class="n">coin</span><span class="p">[</span><span class="s2">&quot;price&quot;</span><span class="p">]</span><span class="si">}</span><span class="s1"> </span><span class="si">{</span><span class="n">coin</span><span class="p">[</span><span class="s2">&quot;symbol&quot;</span><span class="p">]</span><span class="si">}</span><span class="s1"> </span><span class="si">{</span><span class="n">coin</span><span class="p">[</span><span class="s2">&quot;name&quot;</span><span class="p">]</span><span class="si">}</span><span class="s1">&#39;</span><span class="p">)</span> <span class="c1">#this is the way the data is formatted</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>19224.447593601126 BTC Bitcoin
1308.199551212318 ETH Ethereum
1.0000523455427062 USDT Tether USD
1.0002524530884096 USDC USDC
274.74450631272896 BNB Binance Coin
0.5211455214949348 XRP XRP
1.000171247381502 BUSD Binance USD
0.4139552402915634 ADA Cardano
32.454134482189296 SOL Solana
0.06054842848035766 DOGE Dogecoin
6.354403003989721 DOT Polkadot
0.835383532602989 MATIC Polygon
0.000010736474729842 SHIB Shiba Inu
0.999891639898776 DAI Dai
0.06351970963448027 TRX TRON
1308.950203374039 WETH Wrapped Ether
6.352808919826807 UNI Uniswap
16.582266591683975 AVAX Avalanche
4.534812109996118 CAKE PancakeSwap
16.097275035337095 OKB OKB
12.790865904079196 ATOM Cosmos
53.16388872968613 LTC Litecoin
23.87294802061375 FTT FTX Token
25.39839861266645 ETC Ethereum Classic
146.14913616438486 XMR Monero
0.1256703462070973 XLM Stellar
0.32924309203358804 ALGO Algorand
113.34545922204282 BCH Bitcoin Cash
19245.95077301717 BTCB Bitcoin BEP2
0.10541410004274888 CRO Cronos
3.4418393654122696 NEAR NEAR Protocol
0.000293866408536083 LUNC Terra Classic
1.742193550502613 WEMIX WEMIX TOKEN
1.6497345409755526 FLOW Flow
16.524231414902868 ENS EnergySwap
5.292418584086171 FIL Filecoin
0.02320353209595045 VET VeChain
155.68731956157967 QNT Quant
0.6842150594079114 MANA Decentraland
5.624430651470011 ICP Internet Computer (DFINITY)
0.05983121896177806 HBAR Hedera
0.7083305292153628 IMX Immutable X
0.9998613493400573 FRAX Frax
57.322221492067925 EGLD Elrond
1.398063181968517 XTZ Tezos
0.8232983748529789 SAND The Sandbox
0.20047738370702253 CHZ Chiliz
1.340424033760174 LDO Lido DAO Token
5.222843346525186 HT Huobi Token
74.84882436943164 AAVE Aave
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">requests</span>

<span class="n">url</span> <span class="o">=</span> <span class="s2">&quot;https://americanfootballapi.p.rapidapi.com/api/american-football/search/brady&quot;</span>

<span class="n">querystring</span> <span class="o">=</span> <span class="p">{</span><span class="s2">&quot;sort&quot;</span><span class="p">:</span><span class="s2">&quot;new&quot;</span><span class="p">}</span>

<span class="n">headers</span> <span class="o">=</span> <span class="p">{</span>
	<span class="s2">&quot;X-RapidAPI-Key&quot;</span><span class="p">:</span> <span class="s2">&quot;6fa44ed3a2msh483515e3beca32dp153a87jsn04ee72a909e0&quot;</span><span class="p">,</span>
	<span class="s2">&quot;X-RapidAPI-Host&quot;</span><span class="p">:</span> <span class="s2">&quot;americanfootballapi.p.rapidapi.com&quot;</span>
<span class="p">}</span>

<span class="n">response</span> <span class="o">=</span> <span class="n">requests</span><span class="o">.</span><span class="n">request</span><span class="p">(</span><span class="s2">&quot;GET&quot;</span><span class="p">,</span> <span class="n">url</span><span class="p">,</span> <span class="n">headers</span><span class="o">=</span><span class="n">headers</span><span class="p">,</span> <span class="n">params</span><span class="o">=</span><span class="n">querystring</span><span class="p">)</span>

<span class="nb">print</span><span class="p">(</span><span class="n">response</span><span class="o">.</span><span class="n">text</span><span class="p">)</span>
<span class="n">json</span> <span class="o">=</span> <span class="n">response</span><span class="o">.</span><span class="n">json</span><span class="p">()</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="s1">&#39;results&#39;</span><span class="p">)</span>  <span class="c1"># convert response to python json object</span>
 
<span class="c1"># Observe data from an API.  This is how data transports over the internet in a &quot;JSON&quot; text form</span>
<span class="c1"># - The JSON &quot;text&quot; is formed in dictionary {} and list [] divisions</span>
<span class="c1"># - To read the result, Data Scientist of  Developer converts JSON into human readable form</span>
<span class="c1"># - Review the first line, look for the keys --  &quot;status&quot; and &quot;data&quot;</span>

<span class="k">for</span> <span class="n">post</span> <span class="ow">in</span> <span class="n">json</span><span class="p">:</span> <span class="c1"># countries in a list</span>
	<span class="k">for</span> <span class="n">posts</span> <span class="ow">in</span> <span class="n">post</span><span class="p">[</span><span class="s2">&quot;entity&quot;</span><span class="p">]:</span>
		<span class="k">if</span> <span class="n">posts</span><span class="p">[</span><span class="s2">&quot;country&quot;</span><span class="p">]</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="s2">&quot;name&quot;</span><span class="p">)</span> <span class="o">==</span> <span class="s2">&quot;USA&quot;</span><span class="p">:</span>
			<span class="k">for</span> <span class="n">key</span><span class="p">,</span> <span class="n">value</span> <span class="ow">in</span> <span class="n">post</span><span class="o">.</span><span class="n">items</span><span class="p">():</span>
				<span class="nb">print</span><span class="p">(</span><span class="n">key</span><span class="p">,</span> <span class="n">value</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>{&#34;results&#34;:[{&#34;entity&#34;:{&#34;category&#34;:null,&#34;country&#34;:{&#34;alpha2&#34;:&#34;US&#34;,&#34;name&#34;:&#34;USA&#34;},&#34;disabled&#34;:null,&#34;displayInverseHomeAwayTeams&#34;:null,&#34;firstName&#34;:&#34;&#34;,&#34;gender&#34;:null,&#34;id&#34;:853680,&#34;lastName&#34;:&#34;&#34;,&#34;name&#34;:&#34;Tom Brady&#34;,&#34;nameCode&#34;:null,&#34;national&#34;:null,&#34;position&#34;:&#34;QB&#34;,&#34;ranking&#34;:null,&#34;shortName&#34;:&#34;T. Brady&#34;,&#34;slug&#34;:&#34;brady-tom&#34;,&#34;sport&#34;:null,&#34;team&#34;:{&#34;country&#34;:{&#34;alpha2&#34;:&#34;US&#34;,&#34;name&#34;:&#34;USA&#34;},&#34;disabled&#34;:false,&#34;gender&#34;:&#34;M&#34;,&#34;id&#34;:4388,&#34;name&#34;:&#34;Tampa Bay Buccaneers&#34;,&#34;nameCode&#34;:&#34;TB&#34;,&#34;national&#34;:false,&#34;ranking&#34;:null,&#34;shortName&#34;:&#34;Tampa Bay Buccaneers&#34;,&#34;slug&#34;:&#34;tampa-bay-buccaneers&#34;,&#34;sport&#34;:{&#34;id&#34;:63,&#34;name&#34;:&#34;American football&#34;,&#34;slug&#34;:&#34;american-football&#34;},&#34;teamColors&#34;:{&#34;primary&#34;:&#34;#d50a0a&#34;,&#34;secondary&#34;:&#34;#34302b&#34;,&#34;text&#34;:&#34;#34302b&#34;},&#34;type&#34;:0,&#34;userCount&#34;:14077},&#34;teamColors&#34;:null,&#34;type&#34;:null,&#34;userCount&#34;:10394},&#34;score&#34;:1274827,&#34;type&#34;:&#34;player&#34;},{&#34;entity&#34;:{&#34;category&#34;:null,&#34;country&#34;:{&#34;alpha2&#34;:null,&#34;name&#34;:null},&#34;disabled&#34;:null,&#34;displayInverseHomeAwayTeams&#34;:null,&#34;firstName&#34;:&#34;&#34;,&#34;gender&#34;:null,&#34;id&#34;:1132339,&#34;lastName&#34;:&#34;&#34;,&#34;name&#34;:&#34;Brady Christensen&#34;,&#34;nameCode&#34;:null,&#34;national&#34;:null,&#34;position&#34;:&#34;OT&#34;,&#34;ranking&#34;:null,&#34;shortName&#34;:&#34;B. Christensen&#34;,&#34;slug&#34;:&#34;christensen-brady&#34;,&#34;sport&#34;:null,&#34;team&#34;:{&#34;country&#34;:{&#34;alpha2&#34;:&#34;US&#34;,&#34;name&#34;:&#34;USA&#34;},&#34;disabled&#34;:null,&#34;gender&#34;:&#34;M&#34;,&#34;id&#34;:4415,&#34;name&#34;:&#34;Carolina Panthers&#34;,&#34;nameCode&#34;:&#34;CAR&#34;,&#34;national&#34;:false,&#34;ranking&#34;:null,&#34;shortName&#34;:&#34;Carolina Panthers&#34;,&#34;slug&#34;:&#34;carolina-panthers&#34;,&#34;sport&#34;:{&#34;id&#34;:63,&#34;name&#34;:&#34;American football&#34;,&#34;slug&#34;:&#34;american-football&#34;},&#34;teamColors&#34;:{&#34;primary&#34;:&#34;#3a84c5&#34;,&#34;secondary&#34;:&#34;#07141e&#34;,&#34;text&#34;:&#34;#07141e&#34;},&#34;type&#34;:0,&#34;userCount&#34;:2480},&#34;teamColors&#34;:null,&#34;type&#34;:null,&#34;userCount&#34;:2},&#34;score&#34;:205,&#34;type&#34;:&#34;player&#34;},{&#34;entity&#34;:{&#34;category&#34;:null,&#34;country&#34;:{&#34;alpha2&#34;:&#34;US&#34;,&#34;name&#34;:&#34;USA&#34;},&#34;disabled&#34;:null,&#34;displayInverseHomeAwayTeams&#34;:null,&#34;firstName&#34;:null,&#34;gender&#34;:null,&#34;id&#34;:887887,&#34;lastName&#34;:null,&#34;name&#34;:&#34;Brady Sheldon&#34;,&#34;nameCode&#34;:null,&#34;national&#34;:null,&#34;position&#34;:&#34;LB&#34;,&#34;ranking&#34;:null,&#34;shortName&#34;:&#34;B. Sheldon&#34;,&#34;slug&#34;:&#34;sheldon-brady&#34;,&#34;sport&#34;:null,&#34;team&#34;:{&#34;country&#34;:{&#34;alpha2&#34;:null,&#34;name&#34;:null},&#34;disabled&#34;:true,&#34;gender&#34;:null,&#34;id&#34;:273134,&#34;name&#34;:&#34;No team&#34;,&#34;nameCode&#34;:&#34;NTE&#34;,&#34;national&#34;:false,&#34;ranking&#34;:null,&#34;shortName&#34;:&#34;No team&#34;,&#34;slug&#34;:&#34;no-team&#34;,&#34;sport&#34;:{&#34;id&#34;:63,&#34;name&#34;:&#34;American football&#34;,&#34;slug&#34;:&#34;american-football&#34;},&#34;teamColors&#34;:{&#34;primary&#34;:&#34;#52b030&#34;,&#34;secondary&#34;:&#34;#52b030&#34;,&#34;text&#34;:&#34;#ffffff&#34;},&#34;type&#34;:0,&#34;userCount&#34;:0},&#34;teamColors&#34;:null,&#34;type&#34;:null,&#34;userCount&#34;:0},&#34;score&#34;:0,&#34;type&#34;:&#34;player&#34;},{&#34;entity&#34;:{&#34;category&#34;:null,&#34;country&#34;:{&#34;alpha2&#34;:null,&#34;name&#34;:null},&#34;disabled&#34;:null,&#34;displayInverseHomeAwayTeams&#34;:null,&#34;firstName&#34;:null,&#34;gender&#34;:null,&#34;id&#34;:984311,&#34;lastName&#34;:null,&#34;name&#34;:&#34;Tyre Brady&#34;,&#34;nameCode&#34;:null,&#34;national&#34;:null,&#34;position&#34;:&#34;WR&#34;,&#34;ranking&#34;:null,&#34;shortName&#34;:&#34;T. Brady&#34;,&#34;slug&#34;:&#34;brady-tyre&#34;,&#34;sport&#34;:null,&#34;team&#34;:{&#34;country&#34;:{&#34;alpha2&#34;:null,&#34;name&#34;:null},&#34;disabled&#34;:true,&#34;gender&#34;:null,&#34;id&#34;:273134,&#34;name&#34;:&#34;No team&#34;,&#34;nameCode&#34;:&#34;NTE&#34;,&#34;national&#34;:false,&#34;ranking&#34;:null,&#34;shortName&#34;:&#34;No team&#34;,&#34;slug&#34;:&#34;no-team&#34;,&#34;sport&#34;:{&#34;id&#34;:63,&#34;name&#34;:&#34;American football&#34;,&#34;slug&#34;:&#34;american-football&#34;},&#34;teamColors&#34;:{&#34;primary&#34;:&#34;#52b030&#34;,&#34;secondary&#34;:&#34;#52b030&#34;,&#34;text&#34;:&#34;#ffffff&#34;},&#34;type&#34;:0,&#34;userCount&#34;:0},&#34;teamColors&#34;:null,&#34;type&#34;:null,&#34;userCount&#34;:0},&#34;score&#34;:0,&#34;type&#34;:&#34;player&#34;}]}
</pre>
</div>
</div>

<div class="output_area">

<div class="output_subarea output_text output_error">
<pre>
<span class="ansi-red-fg">---------------------------------------------------------------------------</span>
<span class="ansi-red-fg">TypeError</span>                                 Traceback (most recent call last)
<span class="ansi-green-intense-fg ansi-bold">/Users/jameshunter/vscode/james-fastpage/_notebooks/2022-10-06-PBL-python_rapidapi.ipynb Cell 7</span> in <span class="ansi-cyan-fg">&lt;cell line: 22&gt;</span><span class="ansi-blue-fg">()</span>
<span class="ansi-green-intense-fg ansi-bold">     &lt;a href=&#39;vscode-notebook-cell:/Users/jameshunter/vscode/james-fastpage/_notebooks/2022-10-06-PBL-python_rapidapi.ipynb#W6sZmlsZQ%3D%3D?line=21&#39;&gt;22&lt;/a&gt;</span> for post in json: # countries in a list
<span class="ansi-green-intense-fg ansi-bold">     &lt;a href=&#39;vscode-notebook-cell:/Users/jameshunter/vscode/james-fastpage/_notebooks/2022-10-06-PBL-python_rapidapi.ipynb#W6sZmlsZQ%3D%3D?line=22&#39;&gt;23&lt;/a&gt;</span> 	for posts in post[&#34;entity&#34;]:
<span class="ansi-green-fg">---&gt; &lt;a href=&#39;vscode-notebook-cell:/Users/jameshunter/vscode/james-fastpage/_notebooks/2022-10-06-PBL-python_rapidapi.ipynb#W6sZmlsZQ%3D%3D?line=24&#39;&gt;25&lt;/a&gt;</span> 		if posts[&#34;country&#34;].get(&#34;name&#34;) == &#34;USA&#34;:
<span class="ansi-green-intense-fg ansi-bold">     &lt;a href=&#39;vscode-notebook-cell:/Users/jameshunter/vscode/james-fastpage/_notebooks/2022-10-06-PBL-python_rapidapi.ipynb#W6sZmlsZQ%3D%3D?line=25&#39;&gt;26&lt;/a&gt;</span> 			for key, value in post.items():
<span class="ansi-green-intense-fg ansi-bold">     &lt;a href=&#39;vscode-notebook-cell:/Users/jameshunter/vscode/james-fastpage/_notebooks/2022-10-06-PBL-python_rapidapi.ipynb#W6sZmlsZQ%3D%3D?line=26&#39;&gt;27&lt;/a&gt;</span> 				print(key, value)

<span class="ansi-red-fg">TypeError</span>: string indices must be integers</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Formatting-Digital-Coin-example">Formatting Digital Coin example<a class="anchor-link" href="#Formatting-Digital-Coin-example"> </a></h3><blockquote><p>JSON text transferred from the API in the previous cell was converted to a Python Dictionary called json.  The "coins" in the dictionary contain a list of the most relevant data.   Look at the code and comments to see how the original text is turned into something understandable.   Additionally, there are error check to make sure we are starting the code with the expectation that the API was run correctly.</p>
</blockquote>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="sd">&quot;&quot;&quot;</span>
<span class="sd">This cell is dependent on valid run of API above.</span>
<span class="sd">- try and except code is making sure &quot;json&quot; was properly run above</span>
<span class="sd">- inside second try is code that is used to process Coin API data</span>

<span class="sd">Note.  Run this cell repeatedly to format data without re-activating API</span>
<span class="sd">&quot;&quot;&quot;</span>

<span class="k">try</span><span class="p">:</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;JSON data is Python type: &quot;</span> <span class="o">+</span> <span class="nb">str</span><span class="p">(</span><span class="nb">type</span><span class="p">(</span><span class="n">json</span><span class="p">)))</span>
    <span class="k">try</span><span class="p">:</span>
        <span class="c1"># Extracting Coins JSON status, if the API worked</span>
        <span class="n">status</span> <span class="o">=</span> <span class="n">json</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="s1">&#39;status&#39;</span><span class="p">)</span>
        <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;API status: &quot;</span> <span class="o">+</span> <span class="n">status</span><span class="p">)</span>
        <span class="nb">print</span><span class="p">()</span>
        
        <span class="c1"># Extracting Coins JSON data, data about the coins</span>
        <span class="n">data</span> <span class="o">=</span> <span class="n">json</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="s1">&#39;data&#39;</span><span class="p">)</span>
        
        <span class="c1"># Procedural abstraction of Print code for coins</span>
        <span class="k">def</span> <span class="nf">print_coin</span><span class="p">(</span><span class="n">c</span><span class="p">):</span>
            <span class="nb">print</span><span class="p">(</span><span class="n">c</span><span class="p">[</span><span class="s2">&quot;symbol&quot;</span><span class="p">],</span> <span class="n">c</span><span class="p">[</span><span class="s2">&quot;price&quot;</span><span class="p">])</span>
            <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Icon Url: &quot;</span> <span class="o">+</span> <span class="n">c</span><span class="p">[</span><span class="s2">&quot;iconUrl&quot;</span><span class="p">])</span>
            <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Rank Url: &quot;</span> <span class="o">+</span> <span class="n">c</span><span class="p">[</span><span class="s2">&quot;coinrankingUrl&quot;</span><span class="p">])</span>

        <span class="c1"># Coins data was observed to be a list</span>
        <span class="k">for</span> <span class="n">coin</span> <span class="ow">in</span> <span class="n">data</span><span class="p">[</span><span class="s1">&#39;coins&#39;</span><span class="p">]:</span>
            <span class="n">print_coin</span><span class="p">(</span><span class="n">coin</span><span class="p">)</span>
            <span class="nb">print</span><span class="p">()</span>
            
    <span class="k">except</span><span class="p">:</span>
        <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;Did you insert a valid key in X-RapidAPI-Key of API cell above?&quot;</span><span class="p">)</span>
        <span class="nb">print</span><span class="p">(</span><span class="n">json</span><span class="p">)</span>
<span class="k">except</span><span class="p">:</span>
    <span class="nb">print</span><span class="p">(</span><span class="s2">&quot;This cell is dependent on running API call in cell above!&quot;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>JSON data is Python type: &lt;class &#39;dict&#39;&gt;
Did you insert a valid key in X-RapidAPI-Key of API cell above?
{&#39;message&#39;: &#39;You are not subscribed to this API.&#39;}
</pre>
</div>
</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Go-deeper-into-APIs">Go deeper into APIs<a class="anchor-link" href="#Go-deeper-into-APIs"> </a></h3><blockquote><p>Web Development vs Jupyter Notebook.  A notebook is certainly a great place to start.  But, for your end of Trimester project we want you to build the skill to reference and use APIs within your Project.  Here are some resources to get you started with this journey.</p>
</blockquote>
<ul>
<li>In the Nighthawk Coders APCSP you can find an Overview and Examples using APIs:<a href="https://nighthawkcoders.github.io/APCSP/api/overview">APCSP APIs menu</a>- Using Covid RapidAPI<ul>
<li>JavaScript frontend API code in APCSP Fastpages GitHub repo: <a href="https://github.com/nighthawkcoders/APCSP/blob/master/_posts/2022-07-10-PBL-rapidapi.md">https://github.com/nighthawkcoders/APCSP/blob/master/_posts/2022-07-10-PBL-rapidapi.md</a></li>
</ul>
</li>
<li>Making a Jokes API (this will next API tech talk)<ul>
<li>Frontend. JavaScript frontend code in APCSP fastpages GitHub repo: <a href="https://github.com/nighthawkcoders/APCSP/blob/master/_posts/2022-07-10-PBL-jokes.md">https://github.com/nighthawkcoders/APCSP/blob/master/_posts/2022-07-10-PBL-jokes.md</a></li>
<li>Backend Endpoints.  Python code that allows Frontend access: <a href="https://github.com/nighthawkcoders/flask_portfolio/blob/main/api.py">https://github.com/nighthawkcoders/flask_portfolio/blob/main/api.py</a></li>
<li>Backend Jokes Management.  Python code that support Create, Read, Update, Delete (CRUD): <a href="https://github.com/nighthawkcoders/flask_portfolio/blob/main/model_jokes.py">https://github.com/nighthawkcoders/flask_portfolio/blob/main/model_jokes.py</a></li>
</ul>
</li>
</ul>

</div>
</div>
</div>
</div>
 
