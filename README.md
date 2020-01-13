# k8s-usenet

> Usenet + Kubernetes = Heaven.

`k8s-usenet` is a collection of [Helm](https://helm.sh) charts related to [Usenet](https://en.wikipedia.org/wiki/Usenet) services.

## Adding this hub to Helm

Just issue the following command on your terminal in order to add this repository to your Helm repository lists (keep in mind that this repository uses the new V2 version format):

```console
helm repo add k8s-usenet https://raw.githubusercontent.com/aldoborrero/k8s-usenet/master/charts/
```

## Current supported services

- [Bazarr](https://www.bazarr.media/): A companion application to Sonarr and Radarr. It can manage and download subtitles based on your requirements.
- [CouchPotato](https://couchpota.to/): A Video Library Manager for Movies.
- [Jackett](https://github.com/Jackett/Jackett): API Support for your favorite torrent trackers.
- [Headphones](https://github.com/rembo10/headphones): Automatic music downloader for SABnzbd.
- [LazyLibrarian](https://lazylibrarian.gitlab.io/): LazyLibrarian is a program to follow authors and grab metadata for all your digital reading needs.
- [Lidarr](https://github.com/lidarr/lidarr): Looks and smells like Sonarr but made for music.
- [Medusa](https://pymedusa.com/): Automatic Video Library Manager for TV Shows. It watches for new episodes of your favorite shows, and when they are posted it does its magic.
- [Mylar](https://github.com/evilhero/mylar): An automated Comic Book downloader (cbr/cbz) for use with SABnzbd, NZBGet and torrents.
- [Nzbget](https://nzbget.net/): The most efficient usenet downloader.
- [Organizr](https://github.com/causefx/Organizr): HTPC/Homelab Services Organizer.
- [Radarr](https://github.com/Radarr/Radarr): A fork of Sonarr to work with movies à la Couchpotato.
- [Sabnzbd](https://sabnzbd.org/): Free and easy binary newsreader.
- [Sonarr](https://github.com/Sonarr/Sonarr): Smart PVR for newsgroup and bittorrent users.
- [Transmission](https://transmissionbt.com/): A fast, easy and free Bittorrent client.

## Work in progress...

We need more useful Helm charts! Feel free to create a PR in order to contribute with a new service that is not listed above!

## Acknowledgements

- [Jeff Billimek](https://github.com/billimek): For inspiring me to create this repository (some of the Charts here are based [on his awesome work](https://github.com/billimek/billimek-charts)).
- [Alen Komljen](https://github.com/komljen): To whom I copied shamelessly [his Makefile](https://github.com/komljen/helm-charts) to generate a Helm chart repository directly on the repository.

## License

This project is licensed under the Apache 2.0 license. See [LICENSE](LICENSE) for more details.
