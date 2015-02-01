# OpenStack Solr Module

# Quick Start

To install Solr server and configure it with defaults,
include the following in your manifest file:

  class { 'solr':
    solr_dist => 'http://mirror.cc.columbia.edu/pub/software/apache/lucene/solr/4.10.2/solr-4.10.2.tgz',
  }

  solr::core { 'core-default':
  }

# Configuration

## solr::

Deploy and configure the standalone solr application.

    class {'solr':
      solr_dist     => 'http://.../solr-4.10.2.tgz',
      solr_xml_path => '/etc/solr/solr.xml',
    }

## solr::core

Deploy and configure a solr index, accessible for third party
applications.

    solr::core { 'core-default':
      schema_conf_template  => 'solr/core.schema.xml.erb',
      solr_conf_template    => 'solr/core.solrconfig.xml.erb',
      protwords_template    => 'solr/protwords.txt.erb',
      stopwords_template    => 'solr/stopwords.txt.erb',
      stopwords_en_template => 'solr/stopwords_en.txt.erb',
      synonyms_template     => 'solr/synonyms.txt.erb',
    }
