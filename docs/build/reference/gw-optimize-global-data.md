---
title: "/Gw (optimiser les donn&#233;es globales) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Gw"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gw (option du compilateur C++)"
  - "-Gw (option du compilateur C++)"
ms.assetid: 6f90f4e9-5eb8-4c47-886e-631278a5a4a9
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /Gw (optimiser les donn&#233;es globales)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Empaquetez les données globales dans les sections COMDAT pour l'optimisation.  
  
## Syntaxe  
  
```  
/Gw[-]  
```  
  
## Notes  
 L'option **\/Gw** entraine l'empaquetage du compilateur des données globales sur les différentes sections COMDAT.  Par défaut, **\/Gw** est désactivé et doit être explicitement activé.  Pour le désactiver explicitement, utilisez **\/Gw\-**.  Lorsque **\/Gw** et [\/GL](../../build/reference/gl-whole-program-optimization.md) sont activés, l'éditeur de liens utilise l'optimisation de la totalité du programme pour comparer des sections COMDAT sur plusieurs fichiers objets pour exclure des données globales non référencée ou fusionner les données globales en lecture seule identiques.  Cela peut réduire considérablement la taille du fichier exécutable binaire résultant.  
  
 Lorsque vous compilez et liez séparément, vous pouvez utiliser l'option de l'éditeur de liens pour [\/OPT:REF](../../build/reference/opt-optimizations.md) pour exclure du fichier exécutable que les données globales non référencé dans les fichiers objets compilés avec l'option **\/Gw**.  
  
 Utilisez également [\/OPT:ICF](../../build/reference/opt-optimizations.md) et les options de l'éditeur de liens pour [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md) pour fusionner dans le fichier exécutable que les données globales en lecture seule identiques sur plusieurs fichiers objets compilés avec l'option **\/Gw**.  
  
 Pour plus d'informations, consultez [Présentation le commutateur de compilation \/Gw](http://blogs.msdn.com/b/vcblog/archive/2013/09/11/introducing-gw-compiler-switch.aspx) sur le blog de l'équipe Visual C\+\+.  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le dossier **C\/C\+\+**.  
  
3.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
4.  Modifiez la propriété **Options supplémentaires** pour inclure **\/Gw**, puis cliquez sur **OK**.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)