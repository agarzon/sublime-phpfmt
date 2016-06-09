# [phpfmt](https://github.com/phpfmt/fmt) support for Sublime Text 3

***[This project follows a Code of Conduct.](https://github.com/phpfmt/code-of-conduct)***

***[Report issues.](https://github.com/phpfmt/issues)***

### Installation

#### Requirements
- **You must have a running copy of PHP on the machine you are running Sublime Text**

Plugin runs with PHP 7.0 or newer installed in the machine running the plugin.

#### Configuration (OS X and Linux)

- Edit configuration file (`phpfmt.sublime-settings`)
- For field `"php_bin"` enter the path to the php
  Example: `"php_bin":"/usr/local/bin/php"`


#### Windows Support

[Windows support is offered by phpfmtForWindows package.](https://github.com/phpfmt/sublime-phpfmt-for-windows)

### Settings

Prefer using the toggle options at command palette. However you might find yourself in need to setup where PHP is running, use this option below for the configuration file.
```
{
"php_bin":"/usr/local/bin/php",
}
```

### What does it do?

<table>
<tr>
<td>Before</td>
<td>After</td>
</tr>
<tr>
<td>
<pre><code>&lt;?php
for($i = 0; $i &lt; 10; $i++)
{
if($i%2==0)
echo "Flipflop";
}
</code></pre>
</td>
<td>
<pre><code>&lt;?php
for ($i = 0; $i &lt; 10; $i++) {
	if ($i%2 == 0) {
		echo "Flipflop";
	}
}
</code></pre>
</td>
</tr>
<tr>
<td>
<pre><code>&lt;?php
$a = 10;
$otherVar = 20;
$third = 30;
</code></pre>
</td>
<td>
<pre><code>&lt;?php
$a        = 10;
$otherVar = 20;
$third    = 30;
</code></pre>
<i>This can be enabled with the option "enable_auto_align"</i>
</td>
</tr>
<tr>
<td>
<pre><code>&lt;?php
namespace NS\Something;
use \OtherNS\C;
use \OtherNS\B;
use \OtherNS\A;
use \OtherNS\D;

$a = new A();
$b = new C();
$d = new D();
</code></pre>
</td>
<td>
<pre><code>&lt;?php
namespace NS\Something;

use \OtherNS\A;
use \OtherNS\C;
use \OtherNS\D;

$a = new A();
$b = new C();
$d = new D();
</code></pre>
<i>note how it sorts the use clauses, and removes unused ones</i>
</td>
</tr>
</table>

### The Most FAQ

***I want to use sublime-phpfmt, but it needs PHP 7.0 or newer and on my production
server I have PHP 5.6 or older. What should I do?***

Consider installing a standalone PHP 7.0 in a separate directory and have it *not*
configured in the environment. Within the plugin, ensure `php_bin` parameter is pointed to this standalone installation.

### Acknowledgements
- GoSublime - for the method to update the formatted buffer
- Google's diff match patch - http://code.google.com/p/google-diff-match-patch/
