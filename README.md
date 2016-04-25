# webpack
这是一个建立webpack的基本文件包


Skip to content
This repository
Search
Pull requests
Issues
Gist
 @ouyangzhigang
 Unwatch 1
  Star 0
  Fork 0 ouyangzhigang/webpack
 Code  Issues 0  Pull requests 0  Wiki  Pulse  Graphs  Settings
webpack/node_modules/webpack/README.md  
Newer           Older
RawNormal viewHistory  100644  311 lines (224 sloc)  14.6 KB
fca8479webpack base file
ouyang_zhigang authored 5 hours ago
1	[![webpack](https://webpack.github.io/assets/logo.png)](https://webpack.github.io)
2	
3	
4	[![NPM version][npm-image]][npm-url] [![Gitter chat][gitter-image]][gitter-url] [![Downloads][downloads-image]][downloads-url]
5	[![NPM][nodei-image]][nodei-url]
6	
7	build
8	[![Build Status][travis-image]][travis-url] [![Appveyor Status][appveyor-image]][appveyor-url]  [![Coverage Status][coveralls-image]][coveralls-url]
9	
10	dependencies
11	[![Dependency Status][david-image]][david-url] [![devDependency Status][david-dev-image]][david-dev-url] [![peerDependency Status][david-peer-image]][david-peer-url]
12	
13	donation
14	[![gratipay donate button][gratipay-image]][gratipay-url] [![Donate to sokra][donate-image]][donate-url]
15	
16	
17	[documentation](https://webpack.github.io/docs/?utm_source=github&utm_medium=readme&utm_campaign=top)
18	
19	# Introduction
20	
21	webpack is a bundler for modules. The main purpose is to bundle JavaScript
22	files for usage in a browser, yet it is also capable of transforming, bundling,
23	or packaging just about any resource or asset.
24	
25	
26	**TL; DR**
27	
28	* Bundles both [CommonJs](http://www.commonjs.org/specs/modules/1.0/) and [AMD](https://github.com/amdjs/amdjs-api/wiki/AMD) modules (even combined).
29	* Can create a single bundle or multiple chunks that are asynchronously loaded at runtime (to reduce initial loading time).
30	* Dependencies are resolved during compilation reducing the runtime size.
31	* Loaders can preprocess files while compiling, e.g. coffeescript to JavaScript, handlebars strings to compiled functions, images to Base64, etc.
32	* Highly modular plugin system to do whatever else your application requires.
33	
34	# Getting Started
35	
36	Check out webpack's [documentation](https://webpack.github.io/docs/?utm_source=github&utm_medium=readme&utm_campaign=trdr) for quick Getting Started guide, in-depth usage,
37	tutorials and resources.
38	
39	# Installation
40	
41	project:
42	`npm install webpack --save-dev`
43	
44	global:
45	`npm install webpack -g`
46	Usage
47	https://webpack.github.io/docs/tutorials/getting-started/
48	
49	# Examples
50	
51	Take a look at the [`examples`](https://github.com/webpack/webpack/tree/master/examples) folder.
52	
53	# Features
54	
55	## Plugins
56	
57	webpack has a [rich plugin
58	interface](https://webpack.github.io/docs/plugins.html). Most of the features
59	within webpack itself use this plugin interface. This makes webpack very
60	**flexible**.
61	
62	
63	## Performance
64	
65	webpack uses async I/O and has multiple caching levels. This makes webpack fast
66	and incredibly **fast** on incremental compilations.
67	
68	## Loaders
69	
70	webpack enables use of loaders to preprocess files. This allows you to bundle
71	**any static resource** way beyond JavaScript. You can easily [write your own
72	loaders](https://webpack.github.io/docs/loaders.html) using node.js.
73	
74	Loaders are activated by using `loadername!` prefixes in `require()` statements,
75	or are automatically applied via regex from your webpack configuration.
76	
77	Please see [Using Loaders](https://webpack.github.io/docs/using-loaders.html) for more information.
78	
79	**basic**
80	* [`json`](https://github.com/webpack/json-loader): Loads file as JSON
81	* [`raw`](https://github.com/webpack/raw-loader): Loads raw content of a file (as utf-8)
82	* [`val`](https://github.com/webpack/val-loader): Executes code as module and consider exports as JavaScript code
83	* [`script`](https://github.com/webpack/script-loader): Executes a JavaScript file once in global context (like in script tag), requires are not parsed.
84	
85	**packaging**
86	* [`file`](https://github.com/webpack/file-loader): Emits the file into the output folder and returns the (relative) url.
87	* [`url`](https://github.com/webpack/url-loader): The url loader works like the file loader, but can return a Data Url if the file is smaller than a limit.
88	* [`image`](https://github.com/tcoopman/image-webpack-loader): Compresses your images. Ideal to use together with `file` or `url`.
89	* [`svgo-loader`](https://github.com/pozadi/svgo-loader): Compresses SVG images using [svgo](https://github.com/svg/svgo) library
90	* [`baggage`](https://github.com/deepsweet/baggage-loader): Automatically require any resources related to the required one
91	* [`polymer-loader`](https://github.com/JonDum/polymer-loader): Process HTML & CSS with preprocessor of choice and `require()` Web Components like first-class modules.
92	
93	**dialects**
94	* [`coffee`](https://github.com/webpack/coffee-loader): Loads coffee-script like JavaScript
95	* [`babel`](https://github.com/babel/babel-loader): Turn ES6 code into vanilla ES5 using [Babel](https://github.com/babel/babel).
96	* [`livescript`](https://github.com/appedemic/livescript-loader): Loads LiveScript like JavaScript
97	* [`sweetjs`](https://github.com/jlongster/sweetjs-loader): Use sweetjs macros.
98	* [`traceur`](https://github.com/jupl/traceur-loader): Use future JavaScript features with [Traceur](https://github.com/google/traceur-compiler).
99	* [`typescript`](https://github.com/andreypopp/typescript-loader): Loads TypeScript like JavaScript.
100	
101	**templating**
102	* [`html`](https://github.com/webpack/html-loader): Exports HTML as string, require references to static resources.
103	* [`jade`](https://github.com/webpack/jade-loader): Loads jade template and returns a function
104	* [`handlebars`](https://github.com/altano/handlebars-loader): Loads handlebars template and returns a function
105	* [`ractive`](https://github.com/rstacruz/ractive-loader): Pre-compiles Ractive templates for interactive DOM manipulation
106	* [`markdown`](https://github.com/peerigon/markdown-loader): Compiles Markdown to HTML
107	* [`ng-cache`](https://github.com/teux/ng-cache-loader): Puts HTML partials in the Angular's $templateCache
108	
109	**styling**
110	* [`style`](https://github.com/webpack/style-loader): Add exports of a module as style to DOM
111	* [`css`](https://github.com/webpack/css-loader): Loads css file with resolved imports and returns css code
112	* [`cssnext`](https://github.com/cssnext/cssnext-loader): Loads and compiles a css file using [cssnext](http://cssnext.io/)
113	* [`less`](https://github.com/webpack/less-loader): Loads and compiles a less file
114	* [`sass`](https://github.com/jtangelder/sass-loader): Loads and compiles a scss file
115	* [`stylus`](https://github.com/shama/stylus-loader): Loads and compiles a stylus file
116	
117	**misc**
118	* [`po`](https://github.com/dschissler/po-loader): Loads a PO gettext file and returns JSON
119	* [`mocha`](https://github.com/webpack/mocha-loader): Do tests with mocha in browser or node.js
120	* [`eslint`](https://github.com/MoOx/eslint-loader): PreLoader for linting code using ESLint.
121	* [`jshint`](https://github.com/webpack/jshint-loader): PreLoader for linting code.
122	* [`jscs`](https://github.com/unindented/jscs-loader): PreLoader for style checking.
123	* [`injectable`](https://github.com/jauco/webpack-injectable): Allow to inject dependencies into modules
124	* [`transform`](https://github.com/webpack/transform-loader): Use browserify transforms as loader.
125	
126	For the full list of loaders, see [list of loaders](https://webpack.github.io/docs/list-of-loaders.html).
127	
128	## Module Format (AMD/CommonJS)
129	
130	webpack supports **both** AMD and CommonJS module styles. It performs clever static
131	analysis on the AST of your code. It even has an evaluation engine to evaluate
132	simple expressions. This allows you to **support most existing libraries** out of the box.
133	
134	## Code Splitting
135	
136	webpack allows you to split your codebase into multiple chunks. Chunks are
137	loaded asynchronously at runtime. This reduces the initial loading time.
138	
139	[Code Splitting documentation](https://webpack.github.io/docs/code-splitting.html)
140	
141	## Optimizations
142	
143	webpack can do many optimizations to **reduce the output size of your
144	JavaScript** by deduplicating frequently used modules, minifying, and giving
145	you full control of what is loaded initially and what is loaded at runtime
146	through code splitting. It can also can make your code chunks **cache
147	friendly** by using hashes.
148	
149	[Optimization documentation](https://webpack.github.io/docs/optimization.html)
150	
151	webpack optimizes in several ways. It also makes your chunks **cache-friendly** by using hashes.
152	
153	# A small example of what's possible
154	
155	``` javascript
156	// webpack is a module bundler.
157	// This means webpack takes modules with dependencies
158	// and emits static assets representing those modules.
159	
160	// Dependencies can be written in CommonJs
161	var commonjs = require("./commonjs");
162	// or in AMD
163	define(["amd-module", "../file"], function (amdModule, file) {
164		// while previous constructs are sync,
165		// this is async
166		require(["big-module/big/file"], function (big) {
167			 // For async dependencies, webpack splits
168			 // your application into multiple "chunks".
169			 // This part of your application is
170			 // loaded on demand (code-splitting).
171			var stuff = require("../my/stuff");
172			// "../my/stuff" is also loaded on-demand
173			//  because it's in the callback function
174			//  of the AMD require.
175		});
176	});
177	
178	
179	require("coffee!./cup.coffee");
180	// "Loaders" are used to preprocess files.
181	// They can be prefixed in the require call
182	// or configured in the configuration.
183	require("./cup");
184	// This does the same when you add ".coffee" to the extensions
185	// and configure the "coffee" loader for /\.coffee$/
186	
187	function loadTemplate (name) {
188		return require("./templates/" + name + ".jade");
189		// Many expressions are supported in require calls.
190		// A clever parser extracts information and concludes
191		// that everything in "./templates" that matches
192		// /\.jade$/ should be included in the bundle, as it
193		// can be required.
194	}
195	
196	
197	// ...and you can combine everything.
198	function loadTemplateAsync (name, callback) {
199		require(["bundle?lazy!./templates/" + name + ".jade"],
200		  function (templateBundle) {
201		          templateBundle(callback);
202		});
203	}
204	```
205	
206	## Documentation
207	
208	[documentation](https://webpack.github.io/docs/?utm_source=github&utm_medium=readme&utm_campaign=documentation)
209	
210	
211	## Changelog
212	
213	[changelog](https://webpack.github.io/docs/changelog.html)
214	
215	
216	## Tests
217	
218	You can run the Node tests with `npm test`.
219	
220	You can run the browser tests:
221	
222	```
223	cd test/browsertests
224	node build
225	```
226	
227	and open `tests.html` in the browser.
228	
229	## Contribution
230	
231	Most of the time, if webpack is not working correctly for you it is a simple configuration issue.
232	
233	If you are still having difficulty after looking over your configuration carefully, please post
234	a question to [StackOverflow with the webpack tag](http://stackoverflow.com/tags/webpack). Questions
235	that include your webpack.config.js and relevant files are more likely to receive responses.
236	
237	If you have discovered a bug or have a feature suggestion, feel free to create an issue on Github.
238	
239	If you create a loader or plugin, please consider open sourcing it, putting it
240	on NPM and following the `x-loader`, `x-plugin` convention.
241	
242	You are also welcome to correct any spelling mistakes or any language issues.
243	
244	If you want to discuss something or just need help, [here is our gitter.im room](https://gitter.im/webpack/webpack).
245	
246	## License
247	
248	Copyright (c) 2012-2015 Tobias Koppers
249	
250	MIT (http://www.opensource.org/licenses/mit-license.php)
251	
252	## Thanks to
253	
254	(In chronological order)
255	
256	* @google for [Google Web Toolkit (GWT)](https://code.google.com/p/google-web-toolkit), which aims to compile Java to JavaScript. It features a similar [Code Splitting](https://code.google.com/p/google-web-toolkit/wiki/CodeSplitting) as webpack.
257	* @medikoo for [modules-webmake](https://github.com/medikoo/modules-webmake), which is a similar project. webpack was born because I wanted Code Splitting for modules-webpack. Interestingly the [Code Splitting issue is still open](https://github.com/medikoo/modules-webmake/issues/7) (thanks also to @Phoscur for the discussion).
258	* @substack for [browserify](http://browserify.org/), which is a similar project and source for many ideas.
259	* @jrburke for [require.js](http://requirejs.org/), which is a similar project and source for many ideas.
260	* @defunctzombie for the [browser-field spec](https://gist.github.com/defunctzombie/4339901), which makes modules available for node.js, browserify and webpack.
261	* Every early webpack user, which contributed to webpack by writing issues or PRs. You influenced the direction...
262	* @shama, @jhnns and @sokra for maintaining this project
263	* Everyone who has written a loader for webpack. You are the ecosystem...
264	* Everyone I forgot to mention here, but also influenced webpack.
265	
266	
267	## Sponsor
268	
269	This is a free-time project. The time I invest in it fluctuates. If you use webpack for a serious task, and you'd like me to invest more time on it, please donate. This project increases your income/productivity too. It makes development and applications faster and it reduces the required bandwidth.
270	
271	I'm very thankful for every dollar. If you leave your username or email, I may show my thanks by giving you extra support.
272	
273	
274	## Dependencies
275	
276	* [esprima](http://esprima.org/)
277	* [enhanced-resolve](https://github.com/webpack/enhanced-resolve)
278	* [uglify-js](https://github.com/mishoo/UglifyJS)
279	* [mocha](https://github.com/visionmedia/mocha)
280	* [should](https://github.com/visionmedia/should.js)
281	* [optimist](https://github.com/substack/node-optimist)
282	* [async](https://github.com/caolan/async)
283	* [mkdirp](https://github.com/substack/node-mkdirp)
284	* [clone](https://github.com/pvorb/node-clone)
285	
286	
287	[travis-url]: http://travis-ci.org/webpack/webpack
288	[travis-image]: https://img.shields.io/travis/webpack/webpack.svg
289	[appveyor-url]: https://ci.appveyor.com/project/sokra/webpack/branch/master
290	[appveyor-image]: https://ci.appveyor.com/api/projects/status/github/webpack/webpack?svg=true
291	[coveralls-url]: https://coveralls.io/r/webpack/webpack/
292	[coveralls-image]: https://img.shields.io/coveralls/webpack/webpack.svg
293	[npm-url]: https://npmjs.org/package/webpack
294	[npm-image]: https://img.shields.io/npm/v/webpack.svg
295	[downloads-image]: http://img.shields.io/npm/dm/webpack.svg
296	[downloads-url]: http://badge.fury.io/js/webpack
297	[david-url]: https://david-dm.org/webpack/webpack
298	[david-image]: https://img.shields.io/david/webpack/webpack.svg
299	[david-dev-url]: https://david-dm.org/webpack/webpack#info=devDependencies
300	[david-dev-image]: https://david-dm.org/webpack/webpack/dev-status.svg
301	[david-peer-url]: https://david-dm.org/webpack/webpack#info=peerDependencies
302	[david-peer-image]: https://david-dm.org/webpack/webpack/peer-status.svg
303	[nodei-image]: https://nodei.co/npm/webpack.png?downloads=true&downloadRank=true&stars=true
304	[nodei-url]: https://nodei.co/npm/webpack
305	[donate-url]: http://sokra.github.io/
306	[donate-image]: https://img.shields.io/badge/donate-sokra-brightgreen.svg
307	[gratipay-url]: https://gratipay.com/webpack/
308	[gratipay-image]: https://img.shields.io/gratipay/webpack.svg
309	[gitter-url]: https://gitter.im/webpack/webpack
310	[gitter-image]: https://img.shields.io/badge/gitter-webpack%2Fwebpack-brightgreen.svg
Status API Training Shop Blog About
© 2016 GitHub, Inc. Terms Privacy Security Contact Help
