This cops checks the indentation of the here document bodies. The bodies
are indented one step.
In Ruby 2.3 or newer, squiggly heredocs (`<<~`) should be used. If you
use the older rubies, you should introduce some library to your project
(e.g. ActiveSupport, Powerpack or Unindent).

### Example:

    # bad
    <<-RUBY
    something
    RUBY

    # good
    # When EnforcedStyle is squiggly, bad code is auto-corrected to the
    # following code.
    <<~RUBY
      something
    RUBY

    # good
    # When EnforcedStyle is active_support, bad code is auto-corrected to
    # the following code.
    <<-RUBY.strip_heredoc
      something
    RUBY