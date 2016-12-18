---
title: "Applications de bureau Windows (Visual&#160;C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: a020b534-293c-44e2-aa48-516c43ddeb8f
caps.latest.revision: 17
caps.handback.revision: 12
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Applications de bureau Windows (Visual&#160;C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez créer une application de bureau Windows quand vous souhaitez créer une application de bureau native avec une interface utilisateur basée sur des fenêtres, et capable de s’exécuter sur les versions allant de Windows XP à Windows 10.  
  
 Une *application de bureau Windows* \(parfois appelée application Win32 dans les anciennes documentations\) correspond à l’expression classique désignant une application qui utilise des boucles de messages pour traiter les messages Windows directement au lieu d’utiliser une infrastructure telle que Microsoft Foundation Classes \(MFC\), la bibliothèque ATL \(Active Template Library\) ou le .NET Framework. Une application de bureau Windows en C\+\+ peut utiliser des classes et fonctions CRT \(Runtime C\) et STL \(Standard Template Library\), des objets COM, ainsi que toutes les fonctions Windows publiques, rassemblées sous le nom d’API Windows. Pour obtenir une introduction aux applications de bureau Windows en C\+\+, consultez [Apprendre à programmer pour Windows en C\+\+](http://go.microsoft.com/fwlink/p/?LinkId=262281).  
  
 Une application de bureau Windows constitue l’une des manières de créer une application de bureau native pour Windows. L’autre manière consiste à créer une application MFC. MFC est l'option par défaut pour les applications \(en particulier les applications d'entreprise\) qui ont une grande quantité de contrôles d'interface utilisateur ou de contrôles utilisateur personnalisés. MFC fournit des classes d'assistance pratiques pour la sérialisation, la manipulation de texte, l'impression et les éléments d'interface utilisateur modernes tels que le ruban. Ces classes ne sont pas accessibles à une application de bureau Windows.  
  
## Articles connexes  
  
|Titre|Description|  
|-----------|-----------------|  
|[Développement Windows](http://go.microsoft.com/fwlink/p/?LinkId=262282)|Contient des informations sur l'API Windows et COM. \(Certaines API Windows et DLL tierces sont implémentées comme objets COM.\)|  
|[Hilo : développement d’applications C\+\+ pour Windows 7](http://go.microsoft.com/fwlink/p/?LinkId=262284)|Explique comment créer une application de bureau Windows cliente enrichie, qui utilise l’animation Windows et Direct2D pour créer une interface utilisateur de type carrousel.|  
|[Applications console](../windows/console-applications-in-visual-cpp.md)|Contient des informations sur les applications console. Une application console Win32 \(ou Win64\) n’a aucune fenêtre et aucune boucle de message. Elle s'exécute dans la fenêtre de console et l'entrée et la sortie sont gérées via la ligne de commande.|  
|[Visual C\+\+](../top/visual-cpp-in-visual-studio-2015.md)|Décrit les principales fonctionnalités de Visual C\+\+ dans Visual Studio et fournit un lien vers le reste de la documentation Visual C\+\+.|  
|[Centre de développement Visual C\+\+](http://go.microsoft.com/fwlink/p/?LinkId=252885) sur le site web MSDN.|Contient des didacticiels, des billets de blog et des articles relatifs aux applications de bureau Windows.|  
|[Procédure : utilisation du Kit de développement logiciel \(SDK\) Windows 10 dans une application de bureau Windows](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Contient les étapes pour configurer votre projet à générer avec le Kit de développement logiciel \(SDK\) Windows 10.|