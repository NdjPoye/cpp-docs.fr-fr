---
title: "Implementing an STL-Based Collection | Microsoft Docs"
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
  - "ICollectionOnSTLImpl interface"
ms.assetid: 6d49f819-1957-4813-b074-3f12c494d8ca
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Implementing an STL-Based Collection
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL fournit l'interface d' `ICollectionOnSTLImpl` pour vous permettre d'implémenter rapidement les interfaces de collection basées sur de \(STL\) Standard Template Library\) dans vos objets.  Pour comprendre cette classe s'exécute, vous allez via un exemple simple \(ci\-dessous\) qui utilise cette classe pour implémenter en lecture seule des clients Automation visés par collection.  
  
 L'exemple de code est d' [ATLCollections](../top/visual-cpp-samples.md).  
  
 Pour exécuter cette procédure, vous voulez bien :  
  
-   [générez un nouvel objet simple](#vccongenerating_an_object).  
  
-   [Modifiez le fichier IDL](#vcconedit_the_idl) pour l'interface générée.  
  
-   [créez cinq typedefs](#vcconstorage_and_exposure_typedefs) décrivant comment les éléments de collection sont stockés et comment ils sont exposés aux clients via des interfaces COM.  
  
-   [Créez deux typedefs des classes de stratégie de copie](#vcconcopy_classes).  
  
-   [Créez les typedefs pour les implémentations d'énumérateur et de collection](#vcconenumeration_and_collection).  
  
-   [Modifiez le code C\+\+ généré par l'Assistant pour utiliser le typedef de collection](#vcconedit_the_generated_code).  
  
-   [Ajoutez le code pour remplir une collection](#vcconpopulate_the_collection).  
  
##  <a name="vccongenerating_an_object"></a> Générer un nouvel objet simple  
 Créez un projet, garantissant que la zone d'attributs dans les paramètres d'application est supprimé.  Utilisez ATL ajoute la boîte de dialogue de classe et ajoutez l'assistant simple d'objet pour générer un objet simple appelé `Words`.  Assurez\-vous qu'une interface double appelée `IWords` est générée.  Les objets de la classe générée seront utilisés pour représenter une collection de mots \(autrement dit, chaînes\).  
  
##  <a name="vcconedit_the_idl"></a> Modifier le fichier IDL  
 Maintenant, ouvrez le fichier IDL et ajoutez les trois propriétés nécessaires pour transformer `IWords` en interface de la collection en lecture seule, comme indiqué ci\-dessous :  
  
 [!code-cpp[NVC_ATL_COM#24](../atl/codesnippet/CPP/implementing-an-stl-based-collection_1.idl)]  
  
 Il s'agit du formulaire standard pour une interface de la collection en lecture seule conçue avec les clients Automation à l'esprit.  Les commentaires comptabilisés dans cette définition d'interface correspondent aux commentaires ci\-dessous :  
  
1.  Les interfaces de collection sont généralement doubles car les clients Automation accède à la propriété d' `_NewEnum` via **IDispatch::Invoke**.  Toutefois, les clients Automation peuvent accéder aux méthodes restantes via le pointeur vtable, les interfaces doubles sont préférables aux dispinterfaces.  
  
2.  Si une interface double ou une dispinterface n'est pas étendue au moment de l'exécution \(autrement dit, vous fournirez ne pas des méthodes supplémentaires ou des propriétés via **IDispatch::Invoke**\), vous devez appliquer l'attribut de **nonextensible** à la définition.  Cet attribut permet aux clients Automation d'exécuter la vérification complète de code au moment de la compilation.  Dans ce cas, l'interface ne doit pas être étendue.  
  
3.  Le DISPID approprié est important si vous souhaitez que les clients Automation pour pouvoir utiliser cette propriété.  \(Notez qu'il n'existe qu'un trait de soulignement dans **DISPID\_NEWENUM**.\)  
  
4.  Vous pouvez fournir une valeur comme DISPID de la propriété de **Élément** .  Toutefois, **Élément** utilise généralement **DISPID\_VALUE** pour en faire la propriété par défaut de la collection.  Cela permet aux clients Automation pour faire référence à la propriété sans la nommer explicitement.  
  
5.  Le type de données utilisé pour la valeur de retour de la propriété de **Élément** est le type de l'élément enregistré dans la collection en ce qui concerne les clients COM.  L'interface retourne des chaînes, vous devez utiliser le type chaîne standard COM, `BSTR`.  Vous pouvez stocker les données dans un format différent en interne comme vous le constaterez bientôt.  
  
6.  La valeur utilisée pour le DISPID de la propriété de **Nombre** est complètement arbitraire.  Il n'existe aucun DISPID standard pour cette propriété.  
  
##  <a name="vcconstorage_and_exposure_typedefs"></a> Créer des typedefs pour le stockage et l'exposition  
 Une fois que l'interface de la collection est définie, vous devez décider comment les données sont stockées, et comment les données sont exposées via l'énumérateur.  
  
 Les réponses à ces questions peuvent être effectuées sous la forme d'un nombre quelconque de typedef, que vous pouvez ajouter vers le haut du fichier d'en\-tête pour votre classe nouvellement créé :  
  
 [!code-cpp[NVC_ATL_COM#25](../atl/codesnippet/CPP/implementing-an-stl-based-collection_2.h)]  
  
 Dans ce cas, vous stockerez les données sous forme **std::vector** de **std::string**S.  **std::vector** est une classe de conteneur STL qui se comporte comme un tableau managé.  **std::string** est la classe de chaîne de la bibliothèque C\+\+ standard.  Ces classes facilitent à utiliser une collection de chaînes.  
  
 Étant donné que la prise en charge de Visual Basic est essentiel à la réussite de cette interface, l'énumérateur retourné par la propriété d' `_NewEnum` doit prendre en charge l'interface d' **IEnumVARIANT** .  c'est la seule interface d'énumérateur comprise par Visual Basic.  
  
##  <a name="vcconcopy_classes"></a> Créer des typedefs des classes de stratégie de copie  
 Les typedefs que vous avez créés jusqu'à présent fournissent toutes les informations vous devez créer d'autres typedefs pour les classes de copie qui seront utilisées par l'énumérateur et la collection :  
  
 [!code-cpp[NVC_ATL_COM#26](../atl/codesnippet/CPP/implementing-an-stl-based-collection_3.h)]  
  
 Dans cet exemple, vous pouvez utiliser la classe personnalisée d' `GenericCopy` définie dans VCUE\_Copy.h et VCUE\_CopyString.h de l'exemple d' [ATLCollections](../top/visual-cpp-samples.md) .  Vous pouvez utiliser cette classe dans un autre code, mais vous devrez peut\-être définir d'autres spécialisations d' `GenericCopy` pour prendre en charge des types de données utilisés dans vos propres collections.  Pour plus d'informations, consultez [Classes de stratégie de copie ATL](../atl/atl-copy-policy-classes.md).  
  
##  <a name="vcconenumeration_and_collection"></a> Créer des typedefs de l'énumération et la collection  
 Maintenant tous les paramètres de modèle nécessaires pour spécialiser les classes d' `CComEnumOnSTL` et d' `ICollectionOnSTLImpl` pour cette situation ont été fournis sous la forme de typedef.  Pour simplifier l'utilisation des spécialisations, créez deux définitions de types supplémentaires comme indiqué ci\-dessous :  
  
 [!code-cpp[NVC_ATL_COM#27](../atl/codesnippet/CPP/implementing-an-stl-based-collection_4.h)]  
  
 Maintenant `CollectionType` est un synonyme d'une spécialisation d' `ICollectionOnSTLImpl` qui implémente l'interface d' `IWords` définie précédemment et fournit un énumérateur qui prend en charge **IEnumVARIANT**.  
  
##  <a name="vcconedit_the_generated_code"></a> Modifier le code généré par l'Assistant  
 Maintenant vous devez dériver `CWords` de l'implémentation d'interface représentée par le typedef d' `CollectionType` plutôt qu' `IWords`, comme indiqué ci\-dessous :  
  
 [!code-cpp[NVC_ATL_COM#28](../atl/codesnippet/CPP/implementing-an-stl-based-collection_5.h)]  
  
##  <a name="vcconpopulate_the_collection"></a> Ajouter le code pour remplir une collection  
 La seule opération qui reste est de remplir un vecteur à des données.  Dans cet exemple simple, vous pouvez ajouter des mots à la collection dans le constructeur pour la classe :  
  
 [!code-cpp[NVC_ATL_COM#29](../atl/codesnippet/CPP/implementing-an-stl-based-collection_6.h)]  
  
 Maintenant, vous pouvez tester le code avec le client de votre choix.  
  
## Voir aussi  
 [Collections et énumérateurs](../atl/atl-collections-and-enumerators.md)   
 [ATLCollections](../top/visual-cpp-samples.md)   
 [ATL Copy Policy Classes](../atl/atl-copy-policy-classes.md)