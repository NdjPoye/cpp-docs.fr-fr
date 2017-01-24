---
title: "D&#233;rivation d&#39;une classe de CObject | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CObject (classe), dériver de"
  - "CObject (classe), dériver des classes sérialisables"
  - "DECLARE_DYNAMIC (macro)"
  - "DECLARE_DYNCREATE (macro)"
  - "DECLARE_SERIAL (macro)"
  - "classes dérivées, de CObject"
  - "macros (C++), sérialisation"
  - "sérialisation (C++), macros"
ms.assetid: 5ea4ea41-08b5-4bd8-b247-c5de8c152a27
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;rivation d&#39;une classe de CObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article décrit les étapes nécessaires minimales pour faire dériver une classe de [CObject](../mfc/reference/cobject-class.md).  D'autres articles de la classe `CObject` décrivent les étapes nécessaires pour tirer parti des fonctionnalités spécifiques `CObject`, telles que la sérialisation et la prise en charge du débogage de diagnostic.  
  
 Des discussions de `CObject`, les termes « interface le fichier » et « fichier d'implémentation » sont utilisés fréquemment.  Le fichier d'interface \(souvent appelé le fichier d'en\-tête, ou. Le fichier de H\) contient la déclaration de classe et toutes les autres informations nécessaires pour utiliser la classe.  Le fichier d'implémentation \(ou fichier .cpp\) contient la définition de classe ainsi que le code qui implémente le membre de la classe fonctionne.  Par exemple, pour une classe nommée `CPerson`, vous devez créer en général un fichier nommé de l'interface PERSON.H et un fichier d'implémentation nommé PERSON.CPP.  Toutefois, à quelques petites classes qui ne sont pas partagées entre les applications, il est parfois plus facile de combinaison de l'interface et l'implémentation dans un seul fichier .cpp.  
  
 Vous pouvez choisir de quatre niveaux de fonctionnalité de en faisant dériver une classe à partir de `CObject`:  
  
-   Fonctionnalités de base : Aucun support pour plus d'informations sur la classe d'exécution ou de sérialisation mais n'inclut la gestion de la mémoire de diagnostic.  
  
-   Fonctionnalités de base ainsi que la prise en charge des informations sur la classe d'exécution.  
  
-   Fonctionnalités de base ainsi que la prise en charge de la création d'informations sur la classe d'exécution et dynamiques.  
  
-   Les fonctionnalités de base prennent en plus en charge les informations de la classe en exécution, la création dynamique et la sérialisation.  
  
 Les classes conçues pour une réutilisation \(celles qui servira ultérieurement de classes de base\) doivent inclure au moins une prise en charge de la classe d'exécution et la prise en charge de sérialisation, si tout futures besoin de sérialisation est anticipé.  
  
 Choisissez le niveau de fonctionnalité en utilisant des macros spécifiques de déclaration et d'implémentation de la déclaration et l'implémentation des classes que vous faites dériver de `CObject`.  
  
 Le tableau suivant décrit la relation parmi les macros utilisées pour la sérialisation et des informations de support.  
  
### Macros utilisées pour la sérialisation et les informations d'exécution  
  
|Macro utilisée|CObject::IsKindOf|CRuntimeClass::<br /><br /> CreateObject|CArchive::operator\>\><br /><br /> CArchive::operator\<\<|  
|--------------------|-----------------------|--------------------------------------|-------------------------------------------------------|  
|Fonctionnalités de base `CObject`|Non|Non|Non|  
|`DECLARE_DYNAMIC`|Oui|Non|Non|  
|`DECLARE_DYNCREATE`|Oui|Oui|Non|  
|`DECLARE_SERIAL`|Oui|Oui|Oui|  
  
#### Pour utiliser la fonctionnalité de base de CObject  
  
1.  Utilisez la syntaxe régulière C\+\+ pour faire dériver la classe de `CObject` \(ou une classe dérivée de `CObject`\).  
  
     L'exemple suivant illustre le cas le plus simple, la dérivation d'une classe de `CObject`:  
  
     [!code-cpp[NVC_MFCCObjectSample#1](../mfc/codesnippet/CPP/deriving-a-class-from-cobject_1.h)]  
  
 En général, toutefois, vous pouvez remplacer certaines des fonctions membres de `CObject` pour gérer les détails de la nouvelle classe.  Par exemple, vous pouvez généralement substituer la fonction `Dump` par `CObject` pour fournir la sortie de débogage pour le contenu de la classe.  Pour plus d'informations sur la manière de remplacer `Dump`, consultez l'article [Diagnostic : Vider le contenu de l'objet](http://msdn.microsoft.com/fr-fr/727855b1-5a83-44bd-9fe3-f1d535584b59).  Vous pouvez également substituer la fonction `AssertValid` de `CObject` pour fournir le test personnalisé pour valider la cohérence des membres de données d'objets de classe.  Pour une description de la manière de remplacer `AssertValid`, consultez [MFC ASSERT\_VALID et CObject::AssertValid](http://msdn.microsoft.com/fr-fr/7654fb75-9e9a-499a-8165-0a96faf2d5e6).  
  
 L'article [Spécifier les niveaux de fonctionnalité](../mfc/specifying-levels-of-functionality.md) explique comment spécifier d'autres niveaux de fonctionnalité, notamment des informations sur la classe d'exécution, la création d'objets de, et la sérialisation.  
  
## Voir aussi  
 [Utilisation de CObject](../mfc/using-cobject.md)