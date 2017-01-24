---
title: "ATL Copy Policy Classes | Microsoft Docs"
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
  - "_Copy class"
  - "_CopyInterface class"
  - "classes (C++), copy policy"
  - "copy policy classes [C++]"
  - "données (C++), ATL"
ms.assetid: 06704b68-d318-4c5d-a65b-71457fe9d00d
caps.latest.revision: 13
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL Copy Policy Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes de stratégie de copie sont [classes de service](../atl/utility-classes.md) utilisé pour initialiser, copier, et supprimer des données.  Les classes de stratégie de copie vous permettent de définir la sémantique de copie pour un type de données, et pour définir des conversions entre des types de données.  
  
 ATL utilise des classes de stratégie de copie dans ses implémentations des modèles suivants :  
  
-   [CComEnumImpl](../atl/reference/ccomenumimpl-class.md)  
  
-   [IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)  
  
-   [ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)  
  
 En encapsulant les informations nécessaires pour copier ou convertir des données dans une classe de stratégie de copie qui peut être passée comme argument template, les développeurs ATL est attendu la réutilisabilité extrême de ces classes.  Par exemple, si vous devez implémenter une collection à l'aide de n'importe quel type de données arbitraire, tout ce que vous devez fournir est la stratégie de copie appropriée ; vous devez jamais toucher le code qui implémente la collection.  
  
## Définition  
 Par définition, une classe qui fournit les fonctions statiques suivantes est une classe de stratégie de copie :  
  
 `static void init(` `DestinationType` `* p);`  
  
 `static HRESULT copy(` `DestinationType` `* pTo, const`  `SourceType` `* pFrom);`  
  
 `static void destroy(` `DestinationType` `* p);`  
  
 Vous pouvez remplacer les types `DestinationType` et *SourceType* par les types de données arbitraires pour chaque stratégie de copie.  
  
> [!NOTE]
>  Bien que vous puissiez définir des classes de stratégie de copie pour tous les types de données arbitraires, l'utilisation des classes dans le code ATL doit limiter les types qui ont un sens.  Par exemple, lorsque vous utilisez une classe de stratégie de copie avec les implémentations de la collection ou de l'énumérateur ATL, `DestinationType` doit être un type qui peut être utilisé comme paramètre dans une méthode d'interface COM.  
  
 Utilisez **INIT** pour initialiser des données, **copy** pour copier des données, et **destroy** pour libérer les données.  La signification exacte de l'initialisation, la copie, et la destruction sont le champ de la classe de stratégie de copie et varient en fonction de les types de données impliqués.  
  
 Il existe deux spécifications sur l'implémentation d'utilisation d'une classe de stratégie de copie :  
  
-   Le premier paramètre à **copy** doit accepter uniquement un pointeur vers les données que vous avez précédemment initialisées à l'aide de **INIT**.  
  
-   **destroy** doit uniquement jamais recevoir un pointeur vers les données que vous avez précédemment initialisées à l'aide de **INIT** ou avez copiées via **copy**.  
  
## Implémentations standard  
 ATL fournit deux classes de stratégie de copie sous la forme de classes de modèle de **\_Copy** et de **\_CopyInterface** :  
  
-   La classe de **\_Copy** permet de copier homogène uniquement \(pas conversion entre types de données\) parce qu'elle offre uniquement un seul paramètre de modèle pour spécifier `DestinationType` et *SourceType*.  L'implémentation générique de ce modèle ne contient aucune initialisation ou code de destruction et utilise `memcpy` pour copier des données.  ATL fournit également des spécialisations de **\_Copy** pour **variant**, `LPOLESTR`, des types de données d' **OLEVERB**, et de **CONNECTDATA** .  
  
-   La classe de **\_CopyInterface** fournit une implémentation pour copier des pointeurs d'interface qui suivent les règles standard COM.  De nouveau cette classe permet uniquement la copie homogène, elle utilise l'assignation simple et un appel à `AddRef` pour effectuer la copie.  
  
## Implémentations personnalisées  
 En général, vous devrez définir vos propres classes de stratégie de copie de la copie hétérogène \(autrement dit, conversion entre types de données\).  Pour quelques exemples des classes personnalisées de stratégie de copie, examinez les fichiers VCUE\_Copy.h et VCUE\_CopyString.h dans l'exemple de [ATLCollections](../top/visual-cpp-samples.md) .  Ces fichiers contiennent deux classes de stratégie de copie de modèle, `GenericCopy` et `MapCopy`, ainsi que plusieurs spécialisations d' `GenericCopy` pour différents types de données.  
  
### GenericCopy  
 `GenericCopy` vous permet de spécifier *le SourceType* et `DestinationType` comme arguments template.  Voici la forme la plus générale de la classe d' `GenericCopy` de VCUE\_Copy.h :  
  
 [!code-cpp[NVC_ATL_COM#30](../atl/codesnippet/CPP/atl-copy-policy-classes_1.h)]  
  
 VCUE\_Copy.h contient également les spécialisations suivantes de cette classe : `GenericCopy<BSTR>`, `GenericCopy<VARIANT, BSTR>`, `GenericCopy<BSTR, VARIANT>`.  VCUE\_CopyString.h contient les spécialisations de copie de **std::string**s : `GenericCopy<std::string>`, `GenericCopy<VARIANT, std::string>`, et `GenericCopy<BSTR, std::string>`.  Vous pouvez améliorer `GenericCopy` en fournissant d'autres spécialisations de votre choix.  
  
### MapCopy  
 `MapCopy` suppose que les données qui sont copiées sont stockées dans un mappage de style STL, elles vous permettent de spécifier le type de mappage dans lequel les données sont stockées et le type de destination.  L'implémentation de la classe utilise uniquement les typedefs fournis par la classe *de MapType* pour déterminer le type des données sources et appeler la classe appropriée d' `GenericCopy` .  Une spécialisation de cette classe n'est requise.  
  
 [!code-cpp[NVC_ATL_COM#31](../atl/codesnippet/CPP/atl-copy-policy-classes_2.h)]  
  
## Voir aussi  
 [Implementing an STL\-Based Collection](../atl/implementing-an-stl-based-collection.md)   
 [ATLCollections](../top/visual-cpp-samples.md)