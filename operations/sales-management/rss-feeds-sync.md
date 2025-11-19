---
title: "Rss Feeds Sync"
source: "RSS Feeds Sync.docx"
tags: [Customer Documentation]
version: "1.0"
last_updated: "2025-11-17"
short_description: "RSS Feeds Sync We needed a way to read RSS data to be displayed within the NasDisplaySystem"
long_description: "We needed a way to read RSS data to be displayed within the NasDisplaySystem. This has been designed to run as a service so news feed items are downloaded to the market system database. Multiple feeds can be downloaded and these can optionally be filtered so only items within a set time period are stored."
---

RSS Feeds Sync

We needed a way to read RSS data to be displayed within the NasDisplaySystem. This has been designed to run as a service so news feed items are downloaded to the market system database. Multiple feeds can be downloaded and these can optionally be filtered so only items within a set time period are stored.

NasRSSDownloader

NasRSSDownloader is a com visible assembly which reads RSS feeds and stores individual feed items into dot net objects.

RSSFeedSync

RSSFeedSync is a windows service which uses NasMySQL to pickup feeds stored in a MySQL database. RSSFeedsync creates an instance of NasRSSDownloader assembly to read information from the feed. The results returned from the instance are then stored in a MySQL database.

Table structure for this data is as follows:

CREATE TABLE IF NOT EXISTS `rssfeeds` (
  `RSSFeedID` int(11) NOT NULL auto_increment,
  `FeedName` varchar(100) NOT NULL default '',
  `FeedUrl` text NOT NULL,
  `FilterByDate` char(1) NOT NULL default 'Y',
  `FilterMinutes` int(11) NOT NULL default '0',
  `FilterHours` int(11) NOT NULL default '0',
  `FilterDays` int(11) NOT NULL default '1',
  PRIMARY KEY  (`RSSFeedID`)
) ENGINE=MyISAM;

CREATE TABLE IF NOT EXISTS `rssfeedsdata` (
  `RSSFeedItemID` int(11) NOT NULL auto_increment,
  `RSSFeedID` int(11) NOT NULL default '0',
  `PubDate` datetime NOT NULL default '1900-01-01 00:00:00',
  `Title` text NOT NULL,
  `TitleSection` text NOT NULL,
  `TitleWithoutSection` text NOT NULL,
  `Link` text NOT NULL,
  `Description` text NOT NULL,
  PRIMARY KEY  (`RSSFeedItemID`),
  KEY `IndDisplayBoardRSSFeedsData` (`PubDate`,`RSSFeedID`)
) ENGINE=MyISAM;

ConfigureRSSFeedSyncService

ConfigureRSSFeedSyncService is a program for installing the RSSFeedsync service.

The program sets up the necessary settings for the windows service. These settings are stored in the registry under the following key

HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\RSSFeedSync\Parameters

The MySQL Connection the service uses can be configured by clicking the Configure MySQL Connection button. The following form is used for this.

ConfigureRSSFeeds

ConfigureRSSFeeds is a program called off of the NAS command line to configure the RSS feeds that RSSFeedSync reads and stores in the database. If the program is run on the same computer the service resides then a command line argument is not required as the information can be read out of the registry.

Feeds are loaded from the database, refresh feeds will refresh the feeds from the database. Feeds can be added or deleted using the buttons on the toolbar. Feeds can be edited by using the grid. The Feed name is just a description of the feed. The Url is where the feed will be loaded from. The Filter options can be used to limit the results downloaded so the above RSS feeds will only have items for the last day (24 hours) downloaded.

Open Feed will load the Feed Url into a new instance of internet explorer.

View Feeds will show the feeds currently loaded in the database like so