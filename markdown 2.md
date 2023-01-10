Here is a simple flow chart:

```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```

```stl
solid cube_corner
  facet normal 0.0 -1.0 0.0
    outer loop
      vertex 0.0 0.0 0.0
      vertex 1.0 0.0 0.0
      vertex 0.0 0.0 1.0
    endloop
  endfacet
  facet normal 0.0 0.0 -1.0
    outer loop
      vertex 0.0 0.0 0.0
      vertex 0.0 1.0 0.0
      vertex 1.0 0.0 0.0
    endloop
  endfacet
  facet normal -1.0 0.0 0.0
    outer loop
      vertex 0.0 0.0 0.0
      vertex 0.0 0.0 1.0
      vertex 0.0 1.0 0.0
    endloop
  endfacet
  facet normal 0.577 0.577 0.577
    outer loop
      vertex 1.0 0.0 0.0
      vertex 0.0 1.0 0.0
      vertex 0.0 0.0 1.0
    endloop
  endfacet
endsolid
```

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```

```python
def set_password(args):
	password = args.password
	while not password  :
		password1 = getpass("" if args.quiet else "Provide password: ")
		password_repeat = getpass("" if args.quiet else "Repeat password:  ")
		if password1 != password_repeat:
			print("Passwords do not match, try again")
		elif len(password1) < 4:
			print("Please provide at least 4 characters")
		else:
			password = password1

	password_hash = passwd(password)
	cfg = BaseJSONConfigManager(config_dir=jupyter_config_dir())
	cfg.update('jupyter_notebook_config', {
		'NotebookApp': {
			'password': password_hash,
		}
	})
	if not args.quiet:
		print("password stored in config dir: %s" % jupyter_config_dir())

def main(argv):
	parser = argparse.ArgumentParser(argv[0])
	subparsers = parser.add_subparsers()
	parser_password = subparsers.add_parser('password', help='sets a password for your notebook server')
	parser_password.add_argument("password", help="password to set, if not given, a password will be queried for (NOTE: this may not be safe)",
			nargs="?")
	parser_password.add_argument("--quiet", help="suppress messages", action="store_true")
	parser_password.set_defaults(function=set_password)
	args = parser.parse_args(argv[1:])
	args.function(args)
```

```cpp
#include <iostream>
using namespace std;

int main() {    
    int number;

    cout << "Enter an integer: ";
    cin >> number;

    cout << "You entered " << number;    
    return 0;
}
```
