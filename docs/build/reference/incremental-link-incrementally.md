---
title: "/INCREMENTAL (Lier par incr&#233;ment) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/incremental"
  - "VC.Project.VCLinkerTool.LinkIncremental"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/INCREMENTAL (option de l'éditeur de liens)"
  - "INCREMENTAL (option de l'éditeur de liens)"
  - "-INCREMENTAL (option de l'éditeur de liens)"
  - "liaison incrémentielle"
  - "lier par incrément (option)"
  - "LINK (outil C++), options pour effectuer une liaison complète"
ms.assetid: 135656ff-94fa-4ad4-a613-22e1a2a5d16b
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /INCREMENTAL (Lier par incr&#233;ment)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/INCREMENTAL[:NO]  
```  
  
## Notes  
 Contrôle la façon dont l'éditeur gère l'édition des liens incrémentielle.  
  
 Par défaut, l'éditeur de liens s'exécute en mode incrémentiel.  Pour substituer un lien incrémentiel par défaut, spécifiez \/INCREMENTAL:NO.  
  
 Un programme lié de façon incrémentielle équivaut, en termes de fonctionnalités, à un programme lié de façon non incrémentielle.  Toutefois, comme il est préparé aux liens incrémentiels à venir, un fichier exécutable \(.exe\) ou un fichier de bibliothèque de liens dynamiques \(DLL\) lié de façon incrémentielle présente les caractéristiques suivantes :  
  
-   Il est plus volumineux qu'un programme lié de façon non incrémentielle du fait du remplissage du code et des données. \(Le remplissage permet à l'éditeur de liens d'augmenter la taille des fonctions et des données sans recréer le fichier .exe.\)  
  
-   Il peut contenir des conversions de code de renvoi pour gérer le réadressage des fonctions vers de nouvelles adresses.  
  
    > [!NOTE]
    >  Pour vous assurer que la version Release finale ne contient pas de remplissage ou de conversion de code, liez votre programme de façon non incrémentielle.  
  
 Pour lier de façon incrémentielle, indépendamment de la valeur par défaut, spécifiez \/INCREMENTAL.  Lorsque cette option est sélectionnée, l'éditeur de liens émet un avertissement s'il ne peut pas lier de façon incrémentielle, puis lie le programme de façon non incrémentielle.  Certaines options et situations substituent l'option \/INCREMENTAL.  
  
 La plupart des programmes peuvent être liés de façon incrémentielle.  Toutefois, certaines modifications sont trop importantes et certaines options sont incompatibles avec l'édition des liens incrémentielle.  LINK effectue un lien complet si l'une des options suivantes est spécifiée :  
  
-   L'édition des liens incrémentielle n'est pas sélectionnée \(\/INCREMENTAL:NO\)  
  
-   \/OPT:REF est sélectionné  
  
-   \/OPT:ICF est sélectionné  
  
-   \/OPT:LBR est sélectionné  
  
-   \/ORDER est sélectionné  
  
 \/INCREMENTAL est implicite lorsque [\/DEBUG](../../build/reference/debug-generate-debug-info.md) est spécifié.  
  
 De plus, LINK effectue un lien complet si l'une des situations suivantes se produit :  
  
-   Le fichier d'état incrémentiel \(.ilk\) est manquant. \(LINK crée un fichier .ilk en prévision de l'édition des liens incrémentielle à venir\).  
  
-   Le fichier .ilk ne possède pas d'autorisation d'accès en écriture. \(LINK ignore le fichier .ilk et effectue des liens de façon non incrémentielle.\)  
  
-   Le fichier de sortie .exe ou .dll est manquant.  
  
-   L'horodatage du fichier .ilk, .exe ou .dll est modifié.  
  
-   Une option LINK est modifiée.  La plupart des options LINK, lorsqu'elles sont modifiées entre les builds, provoquent un lien complet.  
  
-   Un fichier objet \(.obj\) est ajouté ou omis.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le dossier **Éditeur de liens**.  
  
3.  Sélectionnez la page de propriétés **Général**.  
  
4.  Modifiez la propriété **Activation des liens incrémentiels**.  
  
### Pour définir cette option de l'éditeur de liens par programmation  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkIncremental%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)