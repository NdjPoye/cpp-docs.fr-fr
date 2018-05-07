---
title: Redistribution de la bibliothèque MFC | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, redistributing
- redistributing MFC library
ms.assetid: 72714ce1-385e-4c1c-afa5-96b03e873866
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19a49bf18721f605abe0c6e496d3532012c9c92c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="redistributing-the-mfc-library"></a>Redistribution de la bibliothèque MFC
Si vous liez dynamiquement votre application à la bibliothèque MFC, vous devez redistribuer les DLL MFC correspondant. Par exemple, si votre application MFC est conçue à l’aide de la version de MFC qui est fourni avec Visual Studio 2015, vous devez redistribuer mfc140.dll ou mfc140u.dll, selon que votre application est compilée pour la prise en charge Unicode ou de caractères étroits.  
  
> [!NOTE]
>  Les fichiers mfc140.dll ont été omises dans le répertoire des fichiers redistribuables dans Visual Studio 2015 RTM. Vous pouvez utiliser les versions installées par Visual Studio 2015 dans les répertoires Windows\system32 et Windows\syswow64 à la place.  
  
 Étant donné que toutes les DLL MFC utilisent la version partagée de la bibliothèque de runtime C (CRT), vous devrez également redistribuer la bibliothèque CRT. La version de MFC qui est fourni avec Visual Studio 2015 utilise la bibliothèque CRT universelle, qui est distribuée dans le cadre de Windows 10. Pour exécuter une application MFC générée à l’aide de Visual Studio 2015 sur les versions antérieures de Windows, vous devez redistribuer la bibliothèque Universal CRT. Pour plus d’informations sur comment redistribuer la bibliothèque universal CRT comme un composant du système d’exploitation ou à l’aide d’un déploiement local, consultez [présentation de la bibliothèque Universal CRT](http://go.microsoft.com/fwlink/p/?linkid=617977). Pour télécharger l’Universal CRT pour le déploiement centralisé sur les versions prises en charge de Windows, consultez [Windows 10 universelles C Runtime](http://go.microsoft.com/fwlink/p/?LinkId=619489). Les versions spécifiques à une architecture redistribuables de particulier ucrtbase.dll pour le déploiement local sont trouvent dans le Kit de développement logiciel Windows. Par défaut, Visual Studio installe les composants requis dans C:\Program Files (x86) \Windows Kits\10\Redist\ucrt\DLLs\ dans un sous-répertoire spécifique à l’architecture.  
  
 Si votre application est générée à l’aide d’une version antérieure de la bibliothèque MFC, vous devez redistribuer la DLL CRT correspondant à partir du répertoire de fichiers redistribuables. Par exemple, si votre application MFC est construite à l’aide de l’ensemble d’outils Visual Studio 2013 (vc120), vous devez redistribuer le msvcr120.dll. Vous devrez également redistribuer la bibliothèque mfc correspondante`<version>`u.dll ou mfc`<version>`.dll.  
  
 Si vous liez statiquement votre application à MFC (autrement dit, si vous spécifiez **utiliser les MFC dans une bibliothèque statique** sur la **général** onglet dans le **Pages de propriétés** boîte de dialogue), vous n’avez pas pour redistribuer une DLL MFC. Toutefois, bien que la liaison statique puisse fonctionner pour le test et déploiement interne des applications, il est recommandé que vous ne l’utilisez pas pour redistribuer MFC. Pour plus d’informations sur les stratégies conseillées pour le déploiement des bibliothèques Visual C++, consultez [choix d’une méthode de déploiement](../ide/choosing-a-deployment-method.md).  
  
 Si votre application utilise les classes MFC qui implémentent le contrôle WebBrowser (par exemple, [CHtmlView, classe](../mfc/reference/chtmlview-class.md) ou [CHtmlEditView Class](../mfc/reference/chtmleditview-class.md)), nous recommandons d’installer également la version la plus récente de Microsoft Internet Explorer afin que l’ordinateur cible a les derniers fichiers de contrôle commun. (Au minimum, Internet Explorer 4.0 est requis.) Pour plus d’informations sur l’installation des composants d’Internet Explorer sont disponibles dans « Article 185375 : comment pour créer un unique EXE installer d’Internet Explorer » sur le site Web de Support technique de Microsoft.  
  
 Si votre application utilise les classes de base de données MFC (par exemple, [classe CRecordset](../mfc/reference/crecordset-class.md) et [CRecordView (classe)](../mfc/reference/crecordview-class.md)), vous devez redistribuer ODBC et tous les pilotes ODBC utilisés par votre application. Pour plus d’informations, consultez [redistribution de fichiers de prise en charge de base de données](../ide/redistributing-database-support-files.md).  
  
 Si votre application MFC utilise les contrôles Windows Forms, vous devez redistribuer mfcmifc80.dll avec votre application. Cette DLL est un assembly .NET-signé de nom fort qui peut être redistribué avec une application dans son dossier local d’application ou en le déployant vers le Global Assembly Cache (GAC) à l’aide de la [Gacutil.exe (outil Global Assembly Cache)](/dotnet/framework/tools/gacutil-exe-gac-tool).  
  
 Si vous redistribuez une DLL MFC, veillez à redistribuer la version commerciale et non pas la version debug. Les versions Debug des DLL ne sont pas redistribuables. Les noms des versions debug des DLL MFC terminent par un « d », par exemple, Mfc140d.dll.  
  
 Vous pouvez redistribuer MFC à l’aide soit VCRedist_*architecture*.exe, les modules de fusion sont installés avec Visual Studio, ou en déployant la DLL MFC dans le même dossier que votre application. Pour plus d’informations sur la redistribution de MFC, consultez [redistribution des fichiers Visual C++](../ide/redistributing-visual-cpp-files.md).  
  
## <a name="installation-of-localized-mfc-components"></a>Installation de composants MFC localisés  
 Si vous décidez de localiser votre application en installant une DLL de localisation MFC, vous devez utiliser les fichiers de fusion redistribuables (.msm). Par exemple, si vous souhaitez localiser votre application sur x86 ordinateur, vous devez fusionner Microsoft_VC`<version>`_MFCLOC_x86.msm dans le package d’installation pour x86 ordinateur.  
  
 Les fichiers .msm redistribuable contiennent les DLL qui sont utilisés pour la localisation. Il existe une DLL pour chaque langue prise en charge. Le processus d’installation installe ces DLL dans le dossier %windir%\system32\ sur l’ordinateur cible.  
  
 Pour plus d’informations sur la localisation des applications MFC, consultez [TN057 : localisation des composants MFC](../mfc/tn057-localization-of-mfc-components.md)et également [Article 208983 : l’utilisation des DLL MFC LOC](http://go.microsoft.com/fwlink/p/?linkid=198025) sur le site Web de Support technique de Microsoft.  
  
 Vous pouvez redistribuer les DLL de localisation MFC en déployant la DLL MFC dans le dossier local de votre application. Pour plus d’informations sur la redistribution des bibliothèques Visual C++, consultez [redistribution des fichiers Visual C++](../ide/redistributing-visual-cpp-files.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Redistribution des fichiers Visual C++](../ide/redistributing-visual-cpp-files.md)