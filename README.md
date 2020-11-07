# Wikibase Docker images

[![GitHub Workflow Status](https://img.shields.io/github/workflow/status/ProfessionalWiki/wb-docker/build)](https://github.com/ProfessionalWiki/wb-docker/actions?query=workflow%3Abuild)
[![Docker Image Size (latest semver)](https://img.shields.io/docker/image-size/prowiki/wikibase)](https://hub.docker.com/r/prowiki/wikibase)
[![Docker Pulls](https://img.shields.io/docker/pulls/prowiki/wikibase)](https://hub.docker.com/r/prowiki/wikibase)

This repo contains Dockerfiles to build Wikibase Docker images.

These images differ from the [official Wikibase images](https://github.com/wmde/wikibase-docker) maintained by Wikimedia Deutschland:

* They are build on top of the [MediaWiki image maintained by Professional Wiki](https://github.com/ProfessionalWiki/mw-docker)
* MediaWiki is not installed automatically, like the WMF MediaWiki image, unlike the WMDE Wikibase image
* They contain different extensions
* They do not currently have stable releases

## [prowiki/wikibase](https://hub.docker.com/repository/docker/prowiki/wikibase)

    docker pull prowiki/wikibase:35

<table>
	<tr>
		<th>Image tag</th>
		<th>Description</th>
	</tr>
	<tr>
		<td><a href="https://hub.docker.com/repository/docker/prowiki/wikibase/tags?page=1&name=35">35</a></td>
		<td>Wikibase 1.35.x, PHP 7.4.x, MySQL, Apache</td>
	</tr>
	<tr>
		<td><a href="https://hub.docker.com/repository/docker/prowiki/wikibase/tags?page=1&name=latest">latest</a></td>
		<td>Our most up to date Wikibase image, currently same as 35</td>
	</tr>
</table>
