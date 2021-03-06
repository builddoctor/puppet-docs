Introduction
------------

### Terms

The `namevar` is the parameter used to uniquely identify a type
instance. This is the parameter that gets assigned when a string is
provided before the colon in a type declaration. In general, only
developers will need to worry about which parameter is the
`namevar`.

In the following code:

    file { "/etc/passwd":
        owner => root,
        group => root,
        mode => 644
    }
{:puppet}

`/etc/passwd` is considered the title of the file object (used for
things like dependency handling), and because `path` is the namevar
for `file`, that string is assigned to the `path` parameter.

Parameters
: Determine the specific configuration of the
  instance. They either directly modify the system (internally, these
  are called properties) or they affect how the instance behaves
  (e.g., adding a search path for `exec` instances or determining
  recursion on `file` instances).

Providers
: Provide low-level functionality for a given
  resource type. This is usually in the form of calling out to
  external commands.

  When required binaries are specified for providers, fully qualifed
  paths indicate that the binary must exist at that specific path and
  unqualified binaries indicate that Puppet will search for the
  binary using the shell path.

Features
: The abilities that some providers might not support.
  You can use the list of supported features to determine how a given
  provider can be used.

  Resource types define features they can use, and providers can be
  tested to see which features they provide.

Standard Types
--------------
