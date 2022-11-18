---
title: Get started with QuestDB from the binaries
sidebar_label: Binaries
description:
  How to install and launch QuestDB from the binaries which are available on the
  Get QuestDB page.
---

import CodeBlock from "@theme/CodeBlock"
import InterpolateReleaseData from "../../src/components/InterpolateReleaseData"

This page describes how to install and run QuestDB via binaries. On Linux or FeeBSD, you run QuestDB with the `questdb.sh` script. On Windows, you run the `questdb.exe` executable. For macOS, check out [Homebrew](/docs/get-started/homebrew).

## Prerequisites

### Java 11

You need to have Java 11 installed locally. To check your installed version:

```shell
java -version
```

If you do not have Java installed, install one of the following supported packages for your operating system:

- AdoptOpenJDK
- Amazon Corretto
- OpenJDK
- Oracle Java

Other Java distributions might work but are not tested.

#### `JAVA_HOME`

The environment variable `JAVA_HOME` needs to point to your Java 11 installation
folder.

## Download the binaries

Download the latest binaries from [Get QuestDB](/get-questdb). For release notes, check [GitHub release]({@githubUrl@}/releases).

### Any (no JVM) version

The file is named:

<InterpolateReleaseData
  renderText={(release) => {
    return (
      <CodeBlock className="language-shell">
        {`questdb-${release.name}-no-jre-bin.tar.gz`}
      </CodeBlock>
    )
  }}
/>

### QuestDB version

Depending on your operating system, the file is named:

<!-- prettier-ignore-start -->

import Tabs from "@theme/Tabs"
import TabItem from "@theme/TabItem"

<Tabs defaultValue="linux" values={[
  { label: "Linux", value: "linux" },
  { label: "FreeBSD", value: "bsd" },
  { label: "Windows", value: "windows" },
]}>

<!-- prettier-ignore-end -->

<TabItem value="linux">


<InterpolateReleaseData
  renderText={(release) => {
    return (
      <CodeBlock className="language-shell">
        {`questdb-${release.name}-rt-linux-amd64.tar.gz`}
      </CodeBlock>
    )
  }}
/>

</TabItem>


<TabItem value="bsd">


<InterpolateReleaseData
  renderText={(release) => {
    return (
      <CodeBlock className="language-shell">
        {`questdb-${release.name}-rt-freebsd-amd64.tar.gz`}
      </CodeBlock>
    )
  }}
/>

</TabItem>


<TabItem value="windows">


<InterpolateReleaseData
  renderText={(release) => {
    return (
      <CodeBlock className="language-shell">
        {`questdb-${release.name}-rt-windows-amd64.tar.gz`}
      </CodeBlock>
    )
  }}
/>

</TabItem>


</Tabs>


The Java runtime is packaged directly with QuestDB and you do not need anything else.

## Extract the tarballs

<!-- prettier-ignore-start -->

<Tabs defaultValue="any" values={[
  { label: "Any (no JVM)", value: "any" },
  { label: "QuestDB (Linux)", value: "linux" },
  { label: "QuestDB (FreeBSD)", value: "bsd" },
  { label: "QuestDB (Windows)", value: "windows" },
]}>

<!-- prettier-ignore-end -->

<TabItem value="any">


<InterpolateReleaseData
  renderText={(release) => {
    return (
      <CodeBlock className="language-shell">
        {`tar -xvf questdb-${release.name}-no-jre-bin.tar.gz`}
      </CodeBlock>
    )
  }}
/>

</TabItem>


<TabItem value="linux">


<InterpolateReleaseData
  renderText={(release) => {
    return (
      <CodeBlock className="language-shell">
        {`tar -xvf questdb-${release.name}-rt-linux-amd64.tar.gz`}
      </CodeBlock>
    )
  }}
/>

</TabItem>


<TabItem value="bsd">


<InterpolateReleaseData
  renderText={(release) => {
    return (
      <CodeBlock className="language-shell">
        {`tar -xvf questdb-${release.name}-rt-freebsd-amd64.tar.gz`}
      </CodeBlock>
    )
  }}
/>

</TabItem>


<TabItem value="windows">


<InterpolateReleaseData
  renderText={(release) => {
    return (
      <CodeBlock className="language-shell">
        {`tar -xvf questdb-${release.name}-rt-windows-amd64.tar.gz`}
      </CodeBlock>
    )
  }}
/>

</TabItem>


</Tabs>

## Run QuestDB

<!-- prettier-ignore-start -->

<Tabs defaultValue="nix"
values={[
  { label: "Linux/FreeBSD", value: "nix" },
  { label: "Windows", value: "windows" }
]}>

<!-- prettier-ignore-end -->

<TabItem value="nix">


```shell
./questdb.sh start
```

</TabItem>


<TabItem value="windows">


```shell
questdb.exe start
```

</TabItem>


</Tabs>

### Upgrade QuestDB version

:::note

Check the [release notes](https://github.com/questdb/questdb/releases) and ensure
that necessary [backup](/docs/operations/backup/) is completed.

:::

To upgrade the QuestDB version: stop the instance, overwrite the binaries folder with new binaries, and then restart the instance:

<!-- prettier-ignore-start -->

<Tabs defaultValue="nix"
values={[
  { label: "Linux/FreeBSD", value: "nix" },
  { label: "Windows", value: "windows" }
]}>

<!-- prettier-ignore-end -->

<TabItem value="nix">


```shell
./questdb.sh stop

(Perform the upgrade)

./questdb.sh start
```

</TabItem>


<TabItem value="windows">


```shell
questdb.exe stop

(Perform the upgrade)

questdb.exe start
```

</TabItem>


</Tabs>


## Next steps

Once you extracted the tarball, you are ready to use QuestDB. Navigate to our
[command-line options](/docs/reference/command-line-options) page to learn more
about its usage.
