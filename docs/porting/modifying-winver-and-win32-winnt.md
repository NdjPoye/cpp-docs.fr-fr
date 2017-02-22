---
title: "Modification de WINVER et _WIN32_WINNT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_WIN32_WINNT in an upgraded Visual C++ project"
  - "WINVER in an upgraded Visual C++ project"
ms.assetid: 6a1f1d66-ae0e-48a7-81c3-524d8e8f3447
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Modification de WINVER et _WIN32_WINNT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ ne prend plus en charge le ciblage de Windows 95, Windows 98, Windows ME, Windows NT ou Windows 2000. Si vos macros **WINVER** ou **\_WIN32\_WINNT** sont affectées à l'une de ces versions de Windows, vous devez les changer. Quand vous mettez à niveau un projet créé à l'aide d'une version antérieure de Visual C \+\+, vous pouvez voir s'afficher des erreurs de compilation liées aux macros **WINVER** ou **\_WIN32\_WINNT**, si ces dernières sont affectées à une version de Windows qui n'est plus prise en charge.  
  
## Remarques  
 Pour modifier les macros, ajoutez les lignes suivantes à un fichier d'en\-tête \(par exemple, targetver.h, qui est inclus quand vous créez un projet ciblant Windows\).  
  
```  
#define WINVER 0x0A00 #define _WIN32_WINNT 0x0A00  
```  
  
 Ceci permet de cibler le système d'exploitation Windows 10. Ces valeurs sont répertoriées dans le fichier d'en\-tête Windows SDKDDKVer.h, qui définit également des macros pour chaque version de Windows. Vous devez ajouter l'instruction \#define avant d'inclure SDKDDKVer.h. Voici les lignes de la version Windows 10 de SDKDDKVer.h qui codent les valeurs pour chaque version de Windows :  
  
```  
// // _WIN32_WINNT version constants // #define _WIN32_WINNT_NT4                    0x0400 // Windows NT 4.0 #define _WIN32_WINNT_WIN2K                  0x0500 // Windows 2000 #define _WIN32_WINNT_WINXP                  0x0501 // Windows XP #define _WIN32_WINNT_WS03                   0x0502 // Windows Server 2003 #define _WIN32_WINNT_WIN6                   0x0600 // Windows Vista #define _WIN32_WINNT_VISTA                  0x0600 // Windows Vista #define _WIN32_WINNT_WS08                   0x0600 // Windows Server 2008 #define _WIN32_WINNT_LONGHORN               0x0600 // Windows Vista #define _WIN32_WINNT_WIN7                   0x0601 // Windows 7 #define _WIN32_WINNT_WIN8                   0x0602 // Windows 8 #define _WIN32_WINNT_WINBLUE                0x0603 // Windows 8.1 #define _WIN32_WINNT_WINTHRESHOLD           0x0A00 // Windows 10 #define _WIN32_WINNT_WIN10                  0x0A00 // Windows 10  
```  
  
 Si vous ne voyez pas toutes ces versions de Windows dans votre copie de SDKDDKVer.h, vous utilisez probablement une ancienne version du SDK Windows. Par défaut, les projets Win32 dans [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] utilisent le Kit de développement logiciel \(SDK\) Windows 8.1. Pour utiliser le Kit de développement logiciel \(SDK\) Windows 10, consultez [Procédure : utilisation du Kit de développement logiciel \(SDK\) Windows 10 dans une application de bureau Windows](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md).  
  
> [!NOTE]
>  Il n'est pas certain que les valeurs fonctionnent si vous incluez des en\-têtes MFC internes dans votre application.  
  
 Vous pouvez également définir cette macro à l'aide de l'option de compilateur **\/D**. Pour plus d'informations, consultez [\/D \(Définitions de préprocesseur\)](../build/reference/d-preprocessor-definitions.md).  
  
 Pour plus d’informations sur les significations de ces macros, consultez [Utilisation des en\-têtes Windows](http://msdn.microsoft.com/library/windows/desktop/aa383745).  
  
## Voir aussi  
 [Changements précédents du produit](http://msdn.microsoft.com/fr-fr/91fa1713-0778-4b6b-82f7-0fe0a23ab1db)