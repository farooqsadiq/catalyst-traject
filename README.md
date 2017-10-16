# Catalyst Traject Project

This project provides indexing for catalyst
- Create the solr index from horizon
- Create a temporary mysql table for shelfbrowse

Initially this project was part of the blacklight_rails project


These are configuration and setup files to be used with the
[traject](http://github.com/jrochkind/traject) tool for
indexing MARC to solr.

We also use the [traject_horizon](http://github.com/jrochkind/traject_horizon)
plugin to stream directly from the Horizon database, through traject,
then to Solr.

We use a Gemfile to specify the gems used by our traject process
(probably just the traject_horizon plugin), so use the -G arg
to traject to tell it to use that Gemfile.

traject needs to run under jruby (at least for the configuration we're using),
then for instance:

    traject -G -c ./conf/horizon_source.rb -c ./conf/solr_connect.rb -c ./conf/horizon_index.rb

Or use rake tasks that we might write to control this process.
