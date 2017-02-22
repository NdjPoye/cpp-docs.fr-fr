---
title: "Options, Assistant contr&#244;le ATL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.control.options"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant Contrôle ATL, options"
ms.assetid: 4607c51a-992d-433e-9281-919c6f519a3d
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Options, Assistant contr&#244;le ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Insérez ici le résumé « Résultats de la recherche ».  
  
 Utilisez cette page de l'Assistant pour définir le type de contrôle que vous souhaitez créer et le niveau de prise en charge des interfaces qu'il contient.  
  
## Liste UIElement  
 **Type de contrôle**  
 Type de contrôle que vous souhaitez créer.  
  
-   **Contrôle standard : contrôle ActiveX.**  
  
-   **Contrôle composite** : contrôle ActiveX pouvant contenir \(comme une boîte de dialogue\) d'autres contrôles ActiveX ou Windows.  Un contrôle composite comprend les éléments suivants :  
  
    -   un modèle pour la boîte de dialogue qui implémente le contrôle composite ;  
  
    -   une ressource personnalisée, REGISTRY, qui inscrit automatiquement le contrôle composite lorsqu'il est appelé ;  
  
    -   une classe C\+\+ qui implémente le contrôle composite ;  
  
    -   une interface COM exposée par le contrôle composite ;  
  
    -   une page de test HTML contenant le contrôle composite.  
  
     Par défaut, ce contrôle attribue à [CComControlBase::m\_bWindowOnly](../Topic/CComControlBase::m_bWindowOnly.md) la valeur True, pour indiquer qu'il s'agit d'un contrôle utilisant une fenêtre.  Il implémente une table de récepteurs.  Pour plus d'informations, consultez [Prise en charge pour un contrôle DHTML](../../atl/atl-support-for-dhtml-controls.md).  
  
-   **Contrôle DHTML** : contrôle ATL DHTML spécifie l'interface utilisateur à l'aide de code HTML.  La classe de l'interface utilisateur DHTML contient une table COM.  Par défaut, ce contrôle attribue à [CComControlBase::m\_bWindowOnly](../Topic/CComControlBase::m_bWindowOnly.md) la valeur True, pour indiquer qu'il s'agit d'un contrôle utilisant une fenêtre.  
  
     Pour plus d'informations, consultez [Identifying the Elements of the DHTML Control Project](../../atl/identifying-the-elements-of-the-dhtml-control-project.md).  
  
 **Contrôle minimal**  
 Prend en charge uniquement les interfaces absolument nécessaires à la plupart des conteneurs.  Vous pouvez sélectionner **Contrôle minimal** pour tous les types de contrôles : il est possible de créer un contrôle standard minimal, un contrôle composite minimal ou un contrôle DHTML minimal.  
  
 **Aggregation**  
 Ajoute la prise en charge de l'agrégation pour le contrôle que vous créez.  Pour plus d'informations, consultez [Aggregation](../../atl/aggregation.md).  
  
-   **Oui** : crée un contrôle pouvant être regroupé en agrégats.  
  
-   **Non** : crée un contrôle qui ne peut pas être regroupé en agrégats.  
  
-   **Uniquement** : crée un contrôle qui ne peut être instancié qu'à l'aide de l'agrégation.  
  
 **Modèle de thread**  
 Spécifie le modèle de thread utilisé par le contrôle.  
  
-   **Unique** : le contrôle s'exécute uniquement dans le thread COM principal.  
  
-   **Cloisonné** : le contrôle peut être créé dans n'importe quel mode STA \(Single Thread Apartment\).  Valeur par défaut.  
  
 **Interface**  
 Type d'interface que ce contrôle expose au conteneur.  
  
-   **Double** : crée une interface exposant des propriétés et des méthodes par l'intermédiaire de `IDispatch` et directement par l'intermédiaire du VTBL.  
  
-   **Personnalisé** : crée une interface exposant des méthodes directement par l'intermédiaire d'un VTBL.  
  
     Si vous sélectionnez **Personnalisée**, vous pouvez spécifier que le contrôle est **Compatible Automation**.  Si vous avez sélectionné **Compatible Automation**, l'Assistant ajoute l'attribut [oleautomation](../../windows/oleautomation.md) à l'interface dans l'IDL, et l'interface peut être marshalée par le marshaleur universel dans le fichier oleaut32.dll.  Pour plus d'informations, consultez [Détails de marshaling](http://msdn.microsoft.com/library/windows/desktop/ms692621) dans le [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)].  
  
     Par ailleurs, si vous sélectionnez **Compatible Automation**, tous les paramètres de l'ensemble des méthodes du contrôle doivent être compatibles **VARIANT**.  
  
 **Prise en charge**  
 Définit différentes prises en charge supplémentaires pour le contrôle.  
  
-   **Points de connexion** : active les points de connexion pour votre objet en dérivant la classe de votre objet de [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) et en l'autorisant à exposer une interface source.  
  
-   **Licence** : ajoute la prise en charge des [licences](http://msdn.microsoft.com/library/windows/desktop/ms690543) au contrôle.  Les contrôles sous licence ne peuvent être hébergés que si l'ordinateur client possède la licence adéquate.  
  
## Voir aussi  
 [Assistant Contrôle ATL](../../atl/reference/atl-control-wizard.md)