---
title: "/ERRORREPORT (Signaler les erreurs internes de l&#39;&#201;diteur de liens) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/ERRORREPORT"
  - "VC.Project.VCLinkerTool.ErrorReporting"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ERRORREPORT (option de l'éditeur de liens)"
  - "ERRORREPORT (option de l'éditeur de liens)"
  - "-ERRORREPORT (option de l'éditeur de liens)"
ms.assetid: f5fab595-a2f1-4eb0-ab5c-1c0fbd3d8c28
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /ERRORREPORT (Signaler les erreurs internes de l&#39;&#201;diteur de liens)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/errorReport:[ none | prompt | queue | send ]  
```  
  
## Notes  
 Vous permet de fournir les informations d'erreur interne du compilateur \(Internal Compiler Error ou ICE\) directement à Microsoft.  
  
 L'option **\/errorReport:send** essaie d'envoyer automatiquement les informations sur l'erreur à Microsoft, mais le succès dépend des paramètres du registre.  Pour plus d'informations sur la définition des valeurs appropriées dans le Registre, consultez [Comment activer un signalement automatique d'erreur dans les outils de ligne de commande Visual Studio 2008](http://go.microsoft.com/fwlink/?LinkID=184695) sur le site Web MSDN.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriétés** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Cliquez sur le dossier **Propriétés de configuration**.  
  
3.  Cliquez sur le dossier **Éditeur de liens**.  
  
4.  Cliquez sur la page de propriétés **Avancé**.  
  
5.  Modifiez la propriété **Rapport d'erreurs**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ErrorReporting%2A>.  
  
## Voir aussi  
 [\/errorReport \(Signaler les erreurs internes du compilateur\)](../../build/reference/errorreport-report-internal-compiler-errors.md)   
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)