================================================================================
indent-info.el
================================================================================

Show indentation information in status bar. This is a small minor mode for the
mode-line which places itself inside the ``mode-line-position`` area. It
displays the current indentation mode (Tabs or Spaces) as well as the current
configured ``tab-width``.

You can configure it to map the numbers to different symbols or just displaying
regular numbers. You can also configure the format string to define how you want
the full thing displayed.

Appearance
================================================================================

With spaces:

	.. image:: docs/spaces.png

With tabs:

	.. image:: docs/tabs.png

It can be controlled with the mouse, left click toggles indentation mode, scroll
up and down will change the tab-width within the specified ranges:

	.. image:: docs/mouse-actions.png

Increase/decrease ``tab-width`` by scrolling:

	.. image:: docs/set-tab-width.png

Usage
================================================================================

Put it in your load path and use it with the following code::

	(require 'indent-info)
	(global-indent-info-mode 1)


Key bindings
--------------------------------------------------------------------------------

============ ========================================
    Key      Action
============ ========================================
:kbd:`C-M-~` ``indent-info-toggle-indent-mode``
:kbd:`C-M->` ``indent-info-cycle-tab-width-increase``
:kbd:`C-M-<` ``indent-info-cycle-tab-width-decrease``
============ ========================================

Configuration
================================================================================

It is possible to configure the output to achieve something more to your own
liking.

``indent-info-insert-target``
	Target list for insertion of ``indent-info-mode``.

``indent-info-insert-position``
	Position for insertion of ``indent-info-mode``.

``indent-info-prefix``
	Text to display before the indentation info in the mode line.

``indent-info-suffix``
	Text to display after the indentation info in the mode line.

``indent-info-tab-format``
	Tab indentation format (default: "Tab Size: %s").

``indent-info-space-format``
	Space indentation format (default: "Spaces: %s").

``indent-info-use-symbols``
	Indicates whether to use symbols for the ``tab-width`` number or not.

``indent-info-tab-width-min``
	Min ``tab-width`` for ``tab-width`` cycling (default: 2).

``indent-info-tab-width-max``
	Max ``tab-width`` for ``tab-width`` cycling (default: 8).

``indent-info-tab-width-step``
	Step to use for ``tab-width`` cycling (default: 2).

``indent-info-number-symbol-alist``
	List of ``tab-width`` number mappings.
	Each element is a list of the form ``(NUMBER . SYMBOL)``.

``indent-info-minor-mode-text-properties``
	List of text properties to apply to the ``indent-info`` mode line.

``indent-info-sync-to-editorconfig``
	Sync configuration to editorconfig-mode when updated (default: disabled).

``indent-info-sync-from-editorconfig``
	Sync configuration from editorconfig-mode when updated (default: disabled).

Functions
================================================================================

Three functions are also provided that you can choose to bind to some key.

``indent-info-toggle-indent-mode``
	Toggle indentation modes between tabs and spaces.

``indent-info-cycle-tab-width-increase``
	Cycle ``tab-width`` increasing with ``indent-info-tab-width-step``.
	When reaching ``indent-info-tab-width-max`` it won't do anything.

``indent-info-cycle-tab-width-decrease``
	Cycle ``tab-width`` decreasing with ``indent-info-tab-width-step``.
	When reaching ``indent-info-tab-width-min`` it won't do anything.
