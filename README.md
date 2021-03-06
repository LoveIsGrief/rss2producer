## rss2producer

[![Build Status](http://img.shields.io/travis/nathan-osman/rss2producer.svg)](https://travis-ci.org/nathan-osman/rss2producer)
[![Coverage](http://img.shields.io/coveralls/nathan-osman/rss2producer.svg)](https://coveralls.io/r/nathan-osman/rss2producer)
[![PyPI Version](http://img.shields.io/pypi/v/rss2producer.svg)](https://pypi.python.org/pypi/rss2producer)
[![PyPI Downloads](http://img.shields.io/pypi/dm/rss2producer.svg)](https://pypi.python.org/pypi/rss2producer)
[![License](http://img.shields.io/badge/license-MIT-red.svg)](http://opensource.org/licenses/MIT)

This package provides a Python script with an extremely simple class for
generating an RSS 2.0 feed. With just a couple lines of Python code, your script
can create an RSS 2.0 feed and add items to it.

### Installation

You can install rss2producer via PIP using the following command:

    pip install rss2producer

### Usage

Once installed, you can import the `RSS2Feed` class with the following line:

    from rss2producer import RSS2Feed

To create a feed, simply use the `RSS2Feed` constructor:

    feed = RSS2Feed(
        title='A Simple Title',
        link='http://example.org',
        description='A longer description of the feed contents.'
    )

After the feed is created, you can add items with the `append_item` method:

    feed.append_item(
        title='Sample Item',
        link='http://example.org/sample-item',
        description='A longer description of the sample item.',
        pub_date=datetime.utcnow()
    )

At a minimum, `title` or `description` must be included; all other parameters
are optional. The `pub_date` parameter can be either a `datetime` instance or a
UTC timestamp.

When all of the items have been added to the feed, the XML contents can be
obtained with:

    feed.get_xml()
