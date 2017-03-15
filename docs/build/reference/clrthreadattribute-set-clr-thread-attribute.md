---
title: "/CLRTHREADATTRIBUTE (D&#233;finir l&#39;attribut de thread CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.CLRThreadAttribute"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CLRTHREADATTRIBUTE (option de l'éditeur de liens)"
  - "-CLRTHREADATTRIBUTE (option de l'éditeur de liens)"
ms.assetid: 4907e9ef-5031-446c-aecf-0a0b32fae1e8
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /CLRTHREADATTRIBUTE (D&#233;finir l&#39;attribut de thread CLR)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie explicitement l'attribut de thread pour le point d'entrée de votre programme CLR.  
  
## Syntaxe  
  
```  
/CLRTHREADATTRIBUTE:{STA|MTA|NONE}  
```  
  
#### Paramètres  
 MTA  
 Applique l'attribut MTAThreadAttribute au point d'entrée de votre programme.  
  
 NONE  
 Revient à ne pas spécifier \/CLRTHREADATTRIBUTE.  Permet au Common Language Runtime \(CLR\) de définir l'attribut de thread par défaut.  
  
 STA  
 Applique l'attribut STAThreadAttribute au point d'entrée de votre programme.  
  
## Notes  
 La définition de l'attribut de thread n'est valide que lors de la génération d'un fichier .exe, car il affecte le point d'entrée du thread principal.  
  
 Si vous utilisez le point d'entrée par défaut \(main ou wmain, par exemple\) spécifiez le modèle de thread en utilisant \/CLRTHREADATTRIBUTE ou en plaçant l'attribut de thread \(STAThreadAttribute ou MTAThreadAttribute\) sur la fonction d'entrée par défaut.  
  
 Si vous utilisez un point d'entrée autre que celui par défaut, spécifiez le modèle de thread en utilisant \/CLRTHREADATTRIBUTE ou en plaçant l'attribut de thread sur la fonction d'entrée autre que celle par défaut, puis spécifiez le point d'entrée autre que celui par défaut avec [\/ENTRY](../../build/reference/entry-entry-point-symbol.md).  
  
 Si le modèle de thread spécifié dans le code source n'est pas en accord avec le modèle de thread spécifié à l'aide de \/CLRTHREADATTRIBUTE, l'éditeur de liens ignore \/CLRTHREADATTRIBUTE et applique le modèle de thread spécifié dans le code source.  
  
 Il vous sera nécessaire d'utiliser le monothreading. Par exemple, si votre programme CLR héberge un objet COM qui utilise le monothreading.  Si votre programme CLR utilise le multi\-threading, il ne peut pas héberger d'objet COM qui utilise le monothreading.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Développez le nœud **Propriétés de configuration**.  
  
3.  Développez le nœud **Éditeur de liens**.  
  
4.  Sélectionnez la page de propriétés **Avancé**.  
  
5.  Modifiez la propriété **Attribut de thread CLR**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRThreadAttribute%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)