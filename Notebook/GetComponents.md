## GetComponents

A [[Perl]] script, called GetComponents, was developed to process [[Component Retrieval Language]] files and retrieve the indicated components. Perl was chosen because it is quick, lightweight, and it has a very powerful regular expression engine to parse the component lists.

Given a master thornlist written in a simple Component Retrieval Language (CRL) the script will download/update all necessary thorns.

```bash
./GetComponents --parallel https://bitbucket.org/einsteintoolkit/manifest/raw/ET_2020_11/einsteintoolkit.th
```

## Download

```bash
cd ~/
curl -kLO https://raw.githubusercontent.com/gridaphobe/CRL/ET_2020_11/GetComponents
chmod a+x GetComponents
```

## Developer

- [[Eric Seidel]]