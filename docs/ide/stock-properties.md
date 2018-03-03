---
title: "Propriétés stock | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- stock properties, about stock properties
- stock properties
ms.assetid: a89fc454-0b8e-447a-9033-4c8af46a24d9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9bbc721669d51860c01c760a8d1f9fb899e019e3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="stock-properties"></a>Propriétés stock
Si vous ajoutez une propriété à une dispinterface MFC à l’aide la [Assistant Ajout de propriété](../ide/idl-attributes-add-property-wizard.md), vous pouvez choisir une propriété stock à partir de la **nom de la propriété** liste dans le [noms](../ide/names-add-property-wizard.md) page de la Assistant. Ces propriétés sont les suivantes :  
  
|Nom de propriété|Description|  
|-------------------|-----------------|  
|**Apparence**|Retourne ou définit une valeur qui détermine l’apparence du contrôle. Du contrôle **apparence** propriété peut inclure ou omettre les effets d’un graphique en trois dimensions. Il s’agit d’une propriété ambiante en lecture/écriture.|  
|`BackColor`|Retourne ou définit le contrôle ambiante `BackColor` propriété à une couleur de palette (RVB) ou d’une couleur système prédéfinie. Par défaut, sa valeur correspond à la couleur de premier plan du conteneur du contrôle. Il s’agit d’une propriété ambiante en lecture/écriture.|  
|`BorderStyle`|Retourne ou définit le style de bordure pour un contrôle. Il s’agit d’une propriété en lecture/écriture.|  
|**Légende**|Retourne ou définit le contrôle **légende** propriété. La légende est le titre de la fenêtre. **Légende** n’a pas **variable membre** type d’implémentation.|  
|**Activé**|Retourne ou définit le contrôle **activé** propriété. Un contrôle activé peut répondre aux événements générés par l’utilisateur.|  
|**Police**|Retourne ou définit la police du contrôle ambiante. Null si le contrôle n’a pas de police.|  
|`ForeColor`|Retourne ou définit le contrôle ambiante `ForeColor` propriété.|  
|**hWnd**|Retourne ou définit le contrôle **hWnd** propriété. **hWnd** n’a pas **variable membre** type d’implémentation.|  
|**ReadyState**|Retourne ou définit le contrôle **ReadyState** propriété. Un contrôle peut être non initialisé, initialisé, lors du chargement, interactif ou complet. Consultez [READYSTATE](https://msdn.microsoft.com/en-us/library/aa768362.aspx) dans les *Internet SDK* pour plus d’informations.|  
|**Text**|Retourne ou définit le texte contenu dans un contrôle. **Texte** n’a pas **variable membre** type d’implémentation.|  
  
## <a name="see-also"></a>Voir aussi  
 [Ajout d’une propriété](../ide/adding-a-property-visual-cpp.md)   
 [Attributs IDL, Assistant Ajout de propriété](../ide/idl-attributes-add-property-wizard.md)