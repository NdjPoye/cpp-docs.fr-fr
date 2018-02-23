---
title: Installer un manquant Microsoft Visual C++ Runtime DLL | Documents Microsoft
description: Comment rechercher et installer la DLL du runtime Visual C++ manquantes.
ms.date: 08/30/2017
ms.topic: article
dev_langs:
- C++
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d40e1594b2190d4bbfd2fe52fddaad04af527573
ms.sourcegitcommit: a5a69d2dc3513261e9e28320e4e067aaf40d2ef2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2018
---
# <a name="install-a-missing-microsoft-visual-c-runtime-dll"></a>Installer un manquant Runtime DLL Microsoft Visual C++

Programmes écrits à l’aide de Microsoft Visual C++ souvent nécessitent certains fichiers de bibliothèque runtime Visual C++ supplémentaires, ou des DLL, à exécuter. Ces runtime DLL sont disponibles dans un *Package redistribuable*, un programme d’installation des fichiers de bibliothèque, pour chaque version de Visual C++. Le package redistribuable requis par n’importe quel programme doit être inclus par son programme d’installation. Parfois, si elle n’est pas le cas, vous pouvez installer un package redistribuable vous-même et corriger une erreur système lorsque vous exécutez le programme. 

Vous pouvez indiquer qu’un programme manque dans une DLL d’exécution Visual C++ si vous obtenez une erreur système lorsque vous démarrez le programme indiquant que quelque chose comme « le programme ne peut pas démarrer car VCRuntime140.dll est manquant sur votre ordinateur ». Souvent, il est possible de corriger ce problème, la désinstallation du programme, puis à nouveau d’installer. Nous recommandons de la tentative de cette étape en premier lieu, avant tout autre potentiel correctifs.

Parfois, le package redistribuable est installé par un programme est obsolète. Microsoft fournit des versions mises à jour de la DLL du runtime de temps à autre, pour résoudre des bogues et problèmes de sécurité. Pour maintenir votre ordinateur correctement et en toute sécurité, il est judicieux d’utiliser la dernière mise à jour pour toutes les DLL d’exécution. Vérifiez si un programme d’installation mis à jour est disponible pour votre programme, ce qui peut fournir cette mise à jour pour vous. S’il existe, vous devez ensuite utiliser le programme d’installation mis à jour pour réinstaller votre programme.

Réinstallation de votre programme, l’erreur système ne faire disparaître, puis le programme d’installation du programme peut être rompu ou endommagé, ou la DLL du runtime sur votre ordinateur est peut-être endommagé. Essayez de télécharger une nouvelle copie du programme d’installation de votre programme et l’utiliser pour réinstaller le premier. Si cela ne fonctionne pas, ou un programme d’installation n’est pas disponible, il peut être judicieux de vérifier les installations de Microsoft Visual C++ Redistributable sur votre ordinateur. 

Cette table affiche la liste des DLL qui sont inclus dans un ou plusieurs packages redistribuables, ainsi que des liens pour télécharger une copie du package redistribuable. Avant de télécharger une nouvelle copie d’un package redistribuable, vous devez voir si vous pouvez réparer une installation existante.

|DLL manquant  |Package redistribuable  |
|---------|---------|
|atl80.dll<br />msvcm80.dll<br />msvcp80.dll<br />msvcr80.dll<br />mfc80.dll<br />mfc80u.dll<br />mfcm80.dll<br />mfcm80u.dll|[Microsoft Visual C++ 2005 Redistributable (x86)](https://www.microsoft.com/en-us/download/details.aspx?id=5638)<br />[Microsoft Visual C++ 2005 Redistributable Package (x64)](https://www.microsoft.com/en-us/download/details.aspx?id=18471)<br />[Mise à jour de la sécurité de Microsoft Visual C++ 2005 Service Pack 1 Redistributable Package MFC](https://www.microsoft.com/en-us/download/details.aspx?id=26347)|
|atl90.dll<br />msvcr90.dll<br />msvcm90.dll<br />msvcp90.dll<br />mfc90.dll<br />mfc90u.dll<br />mfcmifc80.dll<br />mfcm90.dll<br />mfcm90u.dll|[Microsoft Visual C++ 2008 Redistributable - x86](https://www.microsoft.com/en-us/download/details.aspx?id=5582)<br />[Microsoft Visual C++ 2008 Redistributable - x64](https://www.microsoft.com/en-us/download/details.aspx?id=2092)<br />[Mise à jour de la sécurité de Microsoft Visual C++ 2008 Service Pack 1 Redistributable Package MFC](https://www.microsoft.com/en-us/download/details.aspx?id=26368)|
|ATL100.dll<br />msvcr100.dll<br />msvcp100.dll<br />msdia71.dll<br />vcomp100.dll<br />mfc100.dll<br />mfc100u.dll<br />mfcmifc80.dll<br />mfcm100.dll<br />mfcm100u.dll|[Microsoft Visual C++ 2010 x86 redistribuable](https://www.microsoft.com/en-us/download/details.aspx?id=8328)<br />[Microsoft Visual C++ 2010 x64 redistribuable](https://www.microsoft.com/en-us/download/details.aspx?id=13523)<br />[Mise à jour de la sécurité de Microsoft Visual C++ 2010 Service Pack 1 Redistributable Package MFC](https://www.microsoft.com/en-us/download/details.aspx?id=26999)|
|atl110.dll<br />msvcr110.dll<br />msvcp110.dll<br />mfc110.dll<br />mfc110u.dll<br />mfcmifc80.dll<br />mfcm110.dll<br />mfcm110u.dll<br />concrt110.dll<br />vccorlib110.dll<br />vcamp110.dll<br />vcomp110.dll|[Microsoft Visual C++ 2012 Redistributable (pour Visual Studio 2012 Update 4)](https://www.microsoft.com/en-us/download/details.aspx?id=30679)|
|msvcr120.dll<br />msvcp120.dll<br />mfc120.dll<br />mfc120u.dll<br />mfcmifc80.dll<br />mfcm120.dll<br />mfcm120u.dll<br />concrt120.dll<br />vccorlib120.dll<br />vcamp120.dll<br />vcomp120.dll|[Microsoft Visual C++ 2013 Redistributable (des liens vers des téléchargements individuels)](https://support.microsoft.com/en-us/help/3179560/update-for-visual-c-2013-and-visual-c-redistributable-package)<br />[Bibliothèque MFC multioctet pour Visual Studio 2013](https://www.microsoft.com/en-us/download/details.aspx?id=40770)<br />[Visual C++ 2013 Runtime pour les applications de chargement de version test Windows 8.1 (téléchargement .zip)](http://download.microsoft.com/download/5/F/0/5F0F8404-9329-44A9-8176-ED6F7F746F25/VCLibs_Redist_Packages.zip)|
|vcruntime140.dll<br />vcruntime140_app.dll<br />msvcp140.dll<br />mfc140.dll<br />mfc140u.dll<br />mfcmifc80.dll<br />mfcm140.dll<br />mfcm140u.dll<br />concrt140.dll<br />vccorlib140.dll<br />vcamp140.dll<br />vcomp140.dll|[Microsoft Visual C++ 2017 (x86) redistribuable](https://go.microsoft.com/fwlink/?LinkId=746571)<br />[Microsoft Visual C++ 2017 (x64) redistribuable](https://go.microsoft.com/fwlink/?LinkId=746572)|
|msvcr100_clr0400.dll<br />msvcr110_clr0400.dll<br />msvcr120_clr0400.dll|[Télécharger le .NET Framework](https://www.microsoft.com/net/download/framework)|

### <a name="to-repair-an-existing-redistributable-package"></a>Pour réparer un package redistribuable existant

1. Ouvrez le panneau de configuration. Dans Windows 10, entrez *le panneau de configuration* dans le bureau rechercher un contrôle dans la barre des tâches, puis choisissez **le panneau de configuration** à partir des choix.

2. Dans le panneau de configuration, choisissez **programmes** > **programmes et fonctionnalités**. Sélectionnez la version de Microsoft Visual C++ Redistributable qui correspond à la DLL est manquante. Si un **modification** bouton s’affiche en haut de la liste, sélectionnez-le. Si le seul choix possible est **désinstallation**, vous ne pouvez pas réparer cette version du package redistribuable.

3. Choisissez **réparation** dans la boîte de dialogue d’installation pour le package redistribuable. Vous devrez peut-être redémarrer lorsque la réparation est terminée. 