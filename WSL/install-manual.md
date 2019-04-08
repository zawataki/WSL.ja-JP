---
title: Linux (WSL) ディストリビューション用 Windows サブシステムを手動でダウンロードします。
description: Linux ディストリビューション用 Windows サブシステムを手動でダウンロードする方法の手順です。
keywords: BashOnWindows、bash、wsl、windows、windows subsystem for linux、WSL では、windows サブシステム、ディストリビューション、ubuntu、openSUSE、SLES、debian、kali
author: taraj
ms.author: taraj
ms.date: 07/24/2018
ms.topic: article
ms.assetid: 9281ffa2-4fa9-4078-bf6f-b51c967617e3
ms.custom: seodec18
ms.openlocfilehash: be1c1331183317d4f970696464110b9968208d21
ms.sourcegitcommit: ca08a78925880ed3eccf88edb30def16c83f2543
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2019
ms.locfileid: "59063570"
---
# <a name="manually-download-windows-subsystem-for-linux-distro-packages"></a><span data-ttu-id="d7062-104">Linux ディストリビューションのパッケージの Windows サブシステムを手動でダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d7062-104">Manually download Windows Subsystem for Linux distro packages</span></span>

<span data-ttu-id="d7062-105">いくつかのシナリオをする可能性がありますいないできる (または) を Microsoft Store を使用して WSL Linux ディストリビューションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d7062-105">There are several scenarios in which you may not be able (or want) to, install WSL Linux distros via the Microsoft Store.</span></span> <span data-ttu-id="d7062-106">具体的を実行して、Windows Server または Microsoft Store、または、企業のネットワーク ポリシーおよび admins 環境内で Microsoft Store の使用を許可しない場合にサポートされていない OS SKU デスクトップの 長期的なサービス (LTSB/LTSC)。</span><span class="sxs-lookup"><span data-stu-id="d7062-106">Specifically, you may be running a Windows Server or Long-Term Servicing (LTSB/LTSC) desktop OS SKU that doesn't support Microsoft Store, or your corporate network policies and/or admins to not permit Microsoft Store usage in your environment.</span></span>

<span data-ttu-id="d7062-107">このような場合は、WSL 自体は、使用可能な方法はダウンロードしてインストールする Linux ディストリビューション WSL でストアにアクセスできない場合ですか。</span><span class="sxs-lookup"><span data-stu-id="d7062-107">In these cases, while WSL itself is available, how do you download and install Linux distros in WSL if you can't access the store?</span></span>

> <span data-ttu-id="d7062-108">注:**Windows 10 S モードで実行する Cmd、PowerShell、および Linux/WSL ディストリビューションをはじめとするコマンド ライン シェル環境は許可されていません**します。</span><span class="sxs-lookup"><span data-stu-id="d7062-108">Note: **Command-line shell environments including Cmd, PowerShell, and Linux/WSL distros are not permitted to run on Windows 10 S Mode**.</span></span> <span data-ttu-id="d7062-109">この制限は、整合性と安全性の目標 S モードを提供することを確認するには存在します。読み取り[この投稿](https://blogs.msdn.microsoft.com/commandline/2017/05/18/will-linux-distros-run-on-windows-10-s/)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="d7062-109">This restriction exists in order to ensure the integrity and safety goals that S Mode delivers: Read [this post](https://blogs.msdn.microsoft.com/commandline/2017/05/18/will-linux-distros-run-on-windows-10-s/) for more information.</span></span>

## <a name="downloading-distros"></a><span data-ttu-id="d7062-110">ディストリビューションをダウンロード</span><span class="sxs-lookup"><span data-stu-id="d7062-110">Downloading distros</span></span>

<span data-ttu-id="d7062-111">Microsoft Store アプリが使用できない場合は、ダウンロードして、これらのリンクをクリックして、Linux ディストリビューションを手動でインストールします。</span><span class="sxs-lookup"><span data-stu-id="d7062-111">If the Microsoft Store app is not available, you can download and manually install Linux distros by clicking these links:</span></span>
* [<span data-ttu-id="d7062-112">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="d7062-112">Ubuntu 18.04</span></span>](https://aka.ms/wsl-ubuntu-1804)
* [<span data-ttu-id="d7062-113">Ubuntu 18.04 ARM</span><span class="sxs-lookup"><span data-stu-id="d7062-113">Ubuntu 18.04 ARM</span></span>](https://aka.ms/wsl-ubuntu-1804-arm)
* [<span data-ttu-id="d7062-114">Ubuntu 16.04</span><span class="sxs-lookup"><span data-stu-id="d7062-114">Ubuntu 16.04</span></span>](https://aka.ms/wsl-ubuntu-1604)
* [<span data-ttu-id="d7062-115">Debian GNU/Linux</span><span class="sxs-lookup"><span data-stu-id="d7062-115">Debian GNU/Linux</span></span>](https://aka.ms/wsl-debian-gnulinux)
* [<span data-ttu-id="d7062-116">Kali Linux</span><span class="sxs-lookup"><span data-stu-id="d7062-116">Kali Linux</span></span>](https://aka.ms/wsl-kali-linux)
* [<span data-ttu-id="d7062-117">OpenSUSE</span><span class="sxs-lookup"><span data-stu-id="d7062-117">OpenSUSE</span></span>](https://aka.ms/wsl-opensuse-42)
* [<span data-ttu-id="d7062-118">SLES</span><span class="sxs-lookup"><span data-stu-id="d7062-118">SLES</span></span>](https://aka.ms/wsl-sles-12)

<span data-ttu-id="d7062-119">これにより、`<distro>.appx`任意のフォルダーにダウンロードするパッケージ。</span><span class="sxs-lookup"><span data-stu-id="d7062-119">This will cause the `<distro>.appx` packages to download to a folder of your choosing.</span></span> <span data-ttu-id="d7062-120">に従って、[インストール手順](#installing-your-distro)ダウンロードした distro(s) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="d7062-120">Follow the [installation instructions](#installing-your-distro) to install your downloaded distro(s).</span></span>

## <a name="downloading-distros-via-the-command-line"></a><span data-ttu-id="d7062-121">コマンドラインを使用してディストリビューションをダウンロード</span><span class="sxs-lookup"><span data-stu-id="d7062-121">Downloading distros via the command line</span></span>
<span data-ttu-id="d7062-122">場合は、コマンドラインを使用して、優先 distro(s) もダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="d7062-122">If you prefer, you can also download your preferred distro(s) via the command line:</span></span>

 ### <a name="download-using-powershell"></a><span data-ttu-id="d7062-123">PowerShell を使用してダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d7062-123">Download using PowerShell</span></span>
 <span data-ttu-id="d7062-124">PowerShell を使用してディストリビューションをダウンロードするには、使用、 [Invoke-webrequest](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.utility/invoke-webrequest)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="d7062-124">To download distros using PowerShell, use the [Invoke-WebRequest](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.utility/invoke-webrequest) cmdlet.</span></span> <span data-ttu-id="d7062-125">Ubuntu 16.04 をダウンロードするサンプル手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d7062-125">Here's a sample instruction to download Ubuntu 16.04.</span></span>

```powershell
Invoke-WebRequest -Uri https://aka.ms/wsl-ubuntu-1604 -OutFile Ubuntu.appx -UseBasicParsing
```

> [!TIP]
> <span data-ttu-id="d7062-126">ダウンロードにかかる時間が長いが場合、設定して、進行状況バーをオフに</span><span class="sxs-lookup"><span data-stu-id="d7062-126">If the download is taking a long time, turn off the progress bar by setting</span></span> `$ProgressPreference = 'SilentlyContinue'`

### <a name="download-using-curl"></a><span data-ttu-id="d7062-127">Curl を使用してダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d7062-127">Download using curl</span></span>
<span data-ttu-id="d7062-128">Windows 10 のスプリング 2018 Update (またはそれ以降) を含む、一般的な[コマンド ライン ユーティリティを curl](https://curl.haxx.se/)をコマンドラインからの web 要求 (つまり HTTP GET、POST、PUT などのコマンド) を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="d7062-128">Windows 10 Spring 2018 Update (or later) includes the popular [curl command-line utility](https://curl.haxx.se/) with which you can invoke web requests (i.e. HTTP GET, POST, PUT, etc. commands) from the command line.</span></span> <span data-ttu-id="d7062-129">使用することができます`curl.exe`上記のディストリビューションをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d7062-129">You can use `curl.exe` to download the above distros:</span></span>

```console
curl.exe -L -o ubuntu-1604.appx https://aka.ms/wsl-ubuntu-1604
```

<span data-ttu-id="d7062-130">上記の例では、`curl.exe`が実行される (だけでなく`curl`)、PowerShell では、実際の curl の実行可能ファイルが呼び出されると、エイリアスの PowerShell curl ではない[Invoke-webrequest](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-6)</span><span class="sxs-lookup"><span data-stu-id="d7062-130">In the above example, `curl.exe` is executed (not just `curl`) to ensure that, in PowerShell, the real curl executable is invoked, not the PowerShell curl alias for [Invoke-WebRequest](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/invoke-webrequest?view=powershell-6)</span></span>

> <span data-ttu-id="d7062-131">注:使用して`curl`が呼び出すスクリプト Cmd シェルを使用してダウンロード手順を実行する必要がある場合に適していますや`.bat`  /  `.cmd`スクリプト。</span><span class="sxs-lookup"><span data-stu-id="d7062-131">Note: Using `curl` might be preferable if you have to invoke/script download steps using Cmd shell and/or `.bat` / `.cmd` scripts.</span></span>

## <a name="installing-your-distro"></a><span data-ttu-id="d7062-132">ディストリビューションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d7062-132">Installing your distro</span></span>
<span data-ttu-id="d7062-133">を、ダウンロードした distro(s) をインストールする方法については、を参照してください、 [Windows デスクトップ](install-win10.md)または[Windows Server](install-on-server.md)インストール手順。</span><span class="sxs-lookup"><span data-stu-id="d7062-133">For instructions on how to install your downloaded distro(s), please refer to the [Windows Desktop](install-win10.md) or [Windows Server](install-on-server.md) installation instructions.</span></span>