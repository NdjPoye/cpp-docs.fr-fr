---
title: "/INTEGRITYCHECK (Exiger la v&#233;rification de la signature) | Microsoft Docs"
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
ms.assetid: 9e738825-2c98-40cd-8ad2-5d0d9c14893e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /INTEGRITYCHECK (Exiger la v&#233;rification de la signature)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie que la signature numérique de l'image binaire doit être vérifiée au moment du chargement.  
  
```  
/INTEGRITYCHECK[:NO]  
```  
  
## Notes  
 Par défaut, **\/INTEGRITYCHECK** est désactivé.  
  
 L'option **\/INTEGRITYCHECK** définit, dans l'en\-tête PE du fichier DLL ou du fichier exécutable, un indicateur qui requiert un contrôle de signature numérique par le gestionnaire de mémoire pour charger l'image dans Windows.  Cette option doit être définie pour les DLL 32 bits et 64 bits qui implémentent un code en mode noyau chargé par certaines fonctionnalités Windows, et est recommandée pour tous les pilotes de périphérique sur Windows Vista, [!INCLUDE[win7](../../build/includes/win7_md.md)], [!INCLUDE[win8](../../build/includes/win8_md.md)], [!INCLUDE[winsvr08](../../build/includes/winsvr08_md.md)] et [!INCLUDE[winserver8](../../build/includes/winserver8_md.md)].  Les versions de Windows antérieures à Windows Vista ignorent cet indicateur.  Pour plus d'informations, consultez [Signature d'intégrité forcée des fichiers Portable Executable \(PE\)](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx).  
  
### Pour définir cette option de l'éditeur de liens dans Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriétés** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Développez le nœud **Propriétés de configuration**.  
  
3.  Développez le nœud **Éditeur de liens**.  
  
4.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
5.  Dans **Options supplémentaires**, entrez `/INTEGRITYCHECK` ou `/INTEGRITYCHECK:NO`.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)   
 [Signature d'intégrité forcée des fichiers Portable Executable \(PE\)](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)   
 [Procédure pas à pas de signature de code en mode noyau](http://msdn.microsoft.com/windows/hardware/gg487328.aspx)   
 [DLL d'AppInit dans Windows 7 et Windows Server 2008](http://msdn.microsoft.com/windows/hardware/gg463040.aspx)