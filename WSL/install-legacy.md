---
title: Windows 10 記念日更新プログラムまたは作成者更新プログラムのインストールまたは削除
description: Windows 10 記念日更新プログラムまたは作成者更新プログラムのインストールとインストール解除の手順 (従来のベータディストリビューション)
keywords: BashOnWindows、bash、wsl、windows、windows subsystem for linux、windowssubsystem、ubuntu、debian、suse、windows 10、legacy、beta、install、remove、uninstall、un/install、delete、deprecated
author: taraj
ms.author: taraj
ms.date: 07/24/2018
ms.topic: article
ms.assetid: 7afaeacf-435a-4e58-bff0-a9f0d75b8a51
ms.custom: seodec18
ms.openlocfilehash: 0d8fdabd61fadbfc58549a220ead23585a3d3656
ms.sourcegitcommit: 5844c6dbf692780b86b30bd65e11820fff43b3bd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67499266"
---
# <a name="guide-to-install-or-uninstall-windows-subsystem-for-linux-on-windows-10-anniversary-update-and-creators-update"></a>Windows 10 記念日更新プログラムおよび作成者の更新プログラムで Windows Subsystem for Linux をインストールまたはアンインストールするためのガイド 

Windows 10 の作成者の更新プログラムまたはそれ以降を実行している場合は、 [windows 10 のインストール手順に従っ](install-win10.md)てください。

<strong><em><span style="color: #f28014">次の手順は、Windows 10 周年更新プログラムまたは Windows 10 の作成者更新プログラムを実行しているユーザーを対象としています。</span></em></strong>

Windows 10 秋の更新プログラム (バージョン 1709) より前のバージョンでは、WSL はベータ機能としてリリースされ、"Bash on Ubuntu on Windows" (または Bash) が最初に実行されたときに1つの Ubuntu インスタンスをインストールしました。

> 以前の Windows 10 リリースでは WSL を使用できますが、このベータ版の "レガシディストリビューション" は廃止されたと見なされるようになりました。 使用可能な Windows 10 の最新バージョンを実行することを強くお勧めします。 新しい Windows 10 のリリースには、WSL 単独で数百の修正と改善が加えられており、WSL でより多くの Linux ツールとアプリが正常に実行できるようになりました。

更新プログラムの適用後にアップグレードできない場合は、次の手順に従って、WSL を有効にして使用します。

1. 開発者モードを有効にして、Windows 10 の記念日更新または作成者の更新で WSL を実行するには、開発者モードを有効にする必要があります。

    **開発者のための**[**設定** -> ] [**更新とセキュリティ** -> ]

    [開発者モード] オプションボタンを選択します。  
    ![開発者モードを有効にする](media/updateAndSecurity.png)

    > 開発者モードを有効にするための要件は、 [Windows 10 の作成者の更新プログラムで削除](https://blogs.msdn.microsoft.com/commandline/2017/06/08/developer-mode-no-longer-required-for-windows-subsystem-for-linux/)されました

1. コマンド プロンプトを開きます。  「 `bash` 」と入力し、enter キーを押します。

    Windows で Bash on Ubuntu を初めて実行すると、正規のライセンスに同意するように求められます。 承諾すると、WSL は Ubuntu インスタンスをコンピューターにダウンロードしてインストールします。また、[Windows の Bash on Ubuntu] ショートカットが [スタート] メニューに追加されます。

    ![Ubuntu のインストールを確認する](media/bashShellInstall.png)

    Windows で Bash on Ubuntu を初めて実行するときに、UNIX ユーザー名とパスワードの作成を求められます。 [新しいディストリビューションインスタンスの指示](initialize-distro.md)に従って、インストールを完了します。

1. 次のいずれかの方法で新しい Ubuntu シェルを起動します。
    * コマンド`bash`プロンプトからの実行
    * [スタート] メニューの [Bash on Ubuntu on Windows] のショートカット

    
## <a name="uninstallingremoving-the-legacy-distro"></a>レガシディストリビューションのアンインストール/削除
WSL をインストールした以前の Windows 10 リリースから Windows 10 にアップグレードすると、既存のディストリビューションはそのまま残ります。 ただし、ストアによって配信される新しいディストリビューションをすぐにインストールし、必要なファイルやデータなどをレガシディストリビューションから新しいディストリビューションに移行することを強くお勧めします。

レガシディストリビューションをコンピューターから削除するには、コマンドラインまたは PowerShell インスタンスから次のコマンドを実行します。

```console
wsl --unregister Legacy
```

Windows バージョン1903以降を使用していない場合は、代わりにまたは`wslconfig /u Legacy` `lxrun /uninstall /full`を実行する必要があります。 

### <a name="manually-deleting-the-legacy-distro"></a>レガシディストリビューションを手動で削除する
必要に応じて、レガシインスタンスを手動で削除できます。 これは、を使用して`lxrun.exe`レガシディストリビューションをアンインストールするときに問題が発生した場合、またはに`lxrun.exe`付属していない Windows 10 Spring 2018 Update (またはそれ以降) を実行している場合に必要になることがあります。

従来の wsl ディストリビューションを強制的に削除するに`%localappdata%\lxss\`は、Windows のエクスプローラーまたはコマンドラインを使用して、フォルダー (およびそのすべてのサブコンテンツ) を削除します。

PowerShell を使用する
```powershell
rm -Recurse $env:localappdata/lxss/
```

Cmd を使用する:
```console
DEL /S %localappdata%\lxss\
```
