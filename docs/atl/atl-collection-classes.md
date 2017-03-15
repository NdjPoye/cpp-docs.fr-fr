---
title: "Classes de collection ATL | Microsoft Docs"
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
helpviewer_keywords: 
  - "classes de collection"
  - "classes de collection, à propos des classes de collection"
  - "classes de collection, choisir"
  - "ConstructElements (fonction)"
  - "CTraits (classes)"
  - "DestructElements (fonction)"
  - "SerializeElements (fonction)"
  - "caractéristiques (classes)"
ms.assetid: 4d619d46-5b4e-41dd-b9fd-e86b1fbc00b5
caps.latest.revision: 14
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes de collection ATL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL fournit de nombreuses classes de stockage et de données accès.  La classe vous décidez d'utiliser dépend de plusieurs facteurs, notamment :  
  
-   La quantité de données à stocker  
  
-   Efficacité et les performances lors de l'accès aux données  
  
-   La capacité d'accéder aux données par index ou par clé  
  
-   Comment les données sont triées  
  
-   Préférence personnelle  
  
## Les classes de collection  
 ATL fournit les classes suivantes de tableau pour traiter un petit nombre d'objets.  Toutefois, ces classes sont limitées et conçues pour être utilisées en interne par ATL.  Il n'est pas recommandé de les utiliser dans vos programmes.  
  
|Classe|Stockage de type de données|  
|------------|---------------------------------|  
|[CSimpleArray](../atl/reference/csimplearray-class.md)|Implémente une classe de tableau pour traiter un petit nombre d'objets.|  
|[CSimpleMap](../atl/reference/csimplemap-class.md)|Implémente une classe de mappage pour traiter un petit nombre d'objets.|  
  
## Classes de collection à caractère général  
 Les classes de traçage implémentent des tableaux, des listes, des cartes et sont fournies en tant que classes de collection à caractère général :  
  
|Classe|Stockage de type de données|  
|------------|---------------------------------|  
|[CAtlArray](../atl/reference/catlarray-class.md)|Implémente un tableau.|  
|[CAtlList](../atl/reference/catllist-class.md)|Implémente une liste.|  
|[CAtlMap](../atl/reference/catlmap-class.md)|Implémente une structure de mappage, par lequel les données puissent être référencées par clé ou la valeur.|  
|[CRBMap](../atl/reference/crbmap-class.md)|Implémente une structure de mappage à l'aide de Rouge\- Noir.|  
|[CRBMultiMap](../atl/reference/crbmultimap-class.md)|Implémente une structure multimapping de Rouge\-Noir.|  
  
 Ces classes intercepteront de nombreuses erreurs de programmation lorsque utilisé dans les versions debug, mais dans l'intéret de performances, ces contrôles ne sont pas exécutées dans les versions commerciales.  
  
## Classes de collection spécialisées  
 Les classes de collection plus spécialisées sont également données pour gérer des pointeurs mémoire et des pointeurs d'interface :  
  
|Classe|Objectif|  
|------------|--------------|  
|[CAutoPtrArray](../atl/reference/cautoptrarray-class.md)|Fournit des méthodes utiles lorsque vous construisez un tableau de pointeurs intelligents.|  
|[CAutoPtrList](../atl/reference/cautoptrlist-class.md)|Fournit des méthodes utiles lorsque vous construisez une liste de pointeurs intelligents.|  
|[CComUnkArray](../atl/reference/ccomunkarray-class.md)|Stocke des pointeurs d' `IUnknown` et est conçu pour être utilisé comme paramètre à la classe de modèle d' [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) .|  
|[CHeapPtrList](../atl/reference/cheapptrlist-class.md)|Fournit des méthodes utiles lorsque vous construisez une liste des pointeurs de tas.|  
|[CInterfaceArray](../atl/reference/cinterfacearray-class.md)|Fournit des méthodes utiles lorsque vous construisez un tableau de pointeurs d'interface COM.|  
|[CInterfaceList](../atl/reference/cinterfacelist-class.md)|Fournit des méthodes utiles lorsque vous construisez une liste des pointeurs d'interface COM.|  
  
## Choisir une classe de collection  
 Chacune des classes de collection disponibles propose différentes caractéristiques de performance, comme indiqué dans le tableau ci\-dessous.  
  
-   Les colonnes 2 et 3 décrivent les caractéristiques de chaque la classe de classement et de l'accès.  Dans le tableau, le terme « taille » signifie que l'ordre dans lequel les éléments sont insérés et supprimés détermine leur ordre dans la collection ; il ne signifie pas que les éléments sont triés sur leur contenu.  Le terme « est indexé » signifie que les éléments de la collection peuvent être extraits par un index d'entiers, comme les éléments d'un tableau classique.  
  
-   Les colonnes 4 et 5 décrivent la représentation de chaque classe.  Dans les applications qui requièrent plusieurs insertions dans la collection, la vitesse d'insertion peut être particulièrement importante ; pour d'autres applications, la vitesse de recherche peut être plus importante.  
  
-   La colonne 6 décrit si chaque formulaire permet les éléments en double.  
  
-   La représentation d'une opération donnée de classe de collection est exprimée en termes de relation entre le temps nécessaire pour terminer l'opération et le nombre d'éléments dans la collection.  Une opération prenant une durée qui augmente linéairement lorsque le nombre d'une augmentation d'éléments est décrit comme O \(n\) algorithme.  En revanche, une opération prenant un certain temps qui augmente inférieur à moins que le nombre d'une augmentation d'éléments est décrit comme O \(algorithme de journal n\).  Par conséquent, en termes de performances, O \(algorithmes de journal n\) surpassent O \(n\) des algorithmes de plus en plus à mesure que le nombre d'éléments augmente.  
  
### Fonctionnalités de forme de collection  
  
|Forme|Priorité ?|Indexé ?|Insérez<br /><br /> element|Recherche<br /><br /> élément spécifié|Dupliqué<br /><br /> éléments ?|  
|-----------|----------------|--------------|-------------------------|------------------------------------|-----------------------------|  
|Liste|Oui|Non|Rapide \(temps fixe\)|Lent o \(n\)|Oui|  
|Tableau|Oui|Par int \(temps fixe\)|Ralentissez O \(n\) sauf si l'insertion à la fin, auquel cas le temps passé dans constante|Lent o \(n\)|Oui|  
|Table|Non|Par clé \(temps fixe\)|Rapide \(temps fixe\)|Rapide \(temps fixe\)|Sans \(clés\) oui \(valeurs\)|  
|Mappage de Rouge\- Noir|Oui \(par la clé\)|Par clé O \(log n\)|o rapide \(log n\)|o rapide \(log n\)|Non|  
|Mappage de plusieurs Rouge\- Noir|Oui \(par la clé\)|Par clé O \(log n\) \(plusieurs valeurs par clé\)|o rapide \(log n\)|o rapide \(log n\)|Oui \(plusieurs valeurs par clé\)|  
  
## À l'aide de objets de CTraits  
 Lorsque les classes de collection ATL peuvent être utilisées pour stocker une large gamme de types de données définis par l'utilisateur, il peut être utile de pouvoir remplacer des fonctions importantes telles que les comparaisons.  Cela est accompli en utilisant les classes de CTraits.  
  
 Les classes de CTraits sont semblables à, mais plus flexibles que, les fonctions d'assistance de classe de collection MFC ; consultez [Programmes d'assistance pour les classes de collection](../mfc/reference/collection-class-helpers.md) pour plus d'informations.  
  
 Lorsque vous construisez votre classe de collection, vous avez la possibilité de spécifier une classe de CTraits.  Cette classe contient le code qui s'exécute des opérations telles que les comparaisons lorsque appelé par les méthodes qui composent la classe de collection.  Par exemple, si votre objet de liste contient vos propres structures définies par l'utilisateur, vous pouvez redéfinir le test d'égalité pour comparer uniquement certaines variables membres.  De cette façon, la méthode de recherche de l'objet de liste sera exécuté de façon plus utile.  
  
## Exemple  
  
### Code  
 [!code-cpp[NVC_ATL_Utilities#112](../atl/codesnippet/CPP/atl-collection-classes_1.cpp)]  
  
## Commentaires  
 Pour une liste des classes de CTraits, consultez [classes de collection](../atl/collection-classes.md).  
  
 Le diagramme suivant illustre la hiérarchie de classes pour les classes de CTraits.  
  
 ![Hiérarchie des traits des classes de collection](../atl/media/vctraitscollectionclasseshierarchy.png "vcTraitsCollectionClassesHierarchy")  
  
## Exemples de classes de collection  
 Les exemples suivants montrent des classes de collection :  
  
-   [Exemple MMXSwarm](../top/visual-cpp-samples.md)  
  
-   [Exemple de DynamicConsumer](../top/visual-cpp-samples.md)  
  
-   [Exemple UpdatePV](../top/visual-cpp-samples.md)  
  
-   [Exemple de bannière](../top/visual-cpp-samples.md)  
  
## Voir aussi  
 [Concepts](../atl/active-template-library-atl-concepts.md)   
 [Classes de collection](../atl/collection-classes.md)