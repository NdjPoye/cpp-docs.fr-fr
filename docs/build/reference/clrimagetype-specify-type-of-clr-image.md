---
title: "/CLRIMAGETYPE (Sp&#233;cifier le type d&#39;une image CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/CLRIMAGETYPE"
  - "VC.Project.VCLinkerTool.CLRImageType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CLRIMAGETYPE (option de l'éditeur de liens)"
  - "-CLRIMAGETYPE (option de l'éditeur de liens)"
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# /CLRIMAGETYPE (Sp&#233;cifier le type d&#39;une image CLR)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/CLRIMAGETYPE:{IJW|PURE|SAFE|SAFE32BITPREFERRED}  
```  
  
## Notes  
 L'éditeur de liens accepte des objets natifs et également des objets MSIL qui sont compilés à l'aide de [\/clr](../../build/reference/clr-common-language-runtime-compilation.md), \/clr:pure, ou \/clr:safe.  Lorsque des objets mixtes dans la même version sont passés, la vérifiabilité du fichier de sortie résultant est, par défaut, au niveau le plus bas de vérifiabilité des modules d'entrée.  Par exemple, si un module safe et un module pure sont passés à l'éditeur de liens, le fichier de sortie sera pure.  Si vous passez une image native et une image en mode mixte \(compilée à l'aide de **\/clr**\), l'image résultante sera une image en mode mixte.  
  
 Utilisez \/CLRIMAGETYPE pour spécifier un niveau de vérifiabilité inférieur, si c'est ce dont vous avez besoin.  
  
 Dans le .NET 4.5, \/CLRIMAGETYPE prend en charge une option SAFE32BITPREFERRED.  Cela paramètre—dans l'en\-tête PE de l'image—des indicateurs image qui montrent les objets MSIL sont sécurisés et peuvent être exécutés sur toutes les plateformes, mais que des environnements 32 bits d'exécution sont préférés.  Cette option permet à une application de s'exécuter sur les plateformes ARM et spécifie également qu'elle devrait fonctionner sous WOW64 sur les systèmes d'exploitation 64 bits au lieu d'utiliser l'environnement 64 bits d'exécution.  
  
 Lors de l'exécution sur un système d'exploitation 64 bits d'un fichier .exe qui a été compilé à l'aide de **\/clr** ou de **\/clr:pure**, l'application s'exécute sous WOW64, permettant ainsi à une application 32 bits de s'exécuter sur un système d'exploitation 64 bits.  Par défaut, un .exe qui est compilé à l'aide de **\/clr:safe** est exécuté sous la prise en charge 64 bits du système d'exploitation.  Toutefois, il est possible que votre application safe charge un composant 32 bits.  Dans ce cas, une image safe qui s'exécute sous la prise en charge 64 bits du système d'exploitation échoue lors du chargement de l'application 32 bits.  Pour vérifier qu'une image sécurisée continue à fonctionner lorsqu'elle charge un composant 32 bits sur un système d'exploitation 64 bits, utilisez l'option \/CLRIMAGETYPE:SAFE32BITPREFERRED.  Si votre code ne doit pas nécessairement s'exécuter sur des plateformes ARM, spécifiez l'option d'\/CLRIMAGETYPE:PURE afin de modifier les métadonnées \(.corflags\), indiquant qu'elle doit s'exécuter sous WOW64 \(et en substituant votre propre symbole d'entrée\) :  
  
 **cl \/clr:safe t.cpp \/link \/clrimagetype:pure \/entry:?main@@$$HYMHXZ \/subsystem:console**  
  
 Pour plus d'informations sur la façon de déterminer le type d'image CLR d'un fichier, consultez [\/CLRHEADER](../../build/reference/clrheader.md).  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Développez le nœud **Propriétés de configuration**.  
  
3.  Développez le nœud **Éditeur de liens**.  
  
4.  Sélectionnez la page de propriétés **Avancé**.  
  
5.  Modifiez la propriété **Type d'image CLR**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)