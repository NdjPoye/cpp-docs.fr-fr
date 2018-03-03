---
title: "Assistant Ajout de méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.method.overview
dev_langs:
- C++
helpviewer_keywords:
- Add Method Wizard [C++]
- methods [C++], adding using wizards
ms.assetid: b9a71b0e-9ecf-40fa-9f86-4200cb23d671
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 63595fe7fda434b7ee16161bd3afdaf8a46fad82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="add-method-wizard"></a>Assistant Ajout de méthode
Utilisez cet Assistant pour ajouter une méthode à une interface. Selon le type de projet ou le type d’interface à laquelle vous ajoutez une méthode, l’Assistant affiche les différentes options.  
  
## <a name="names"></a>Noms  
 **Type de retour**  
 Le type de données retourné par la méthode. `HRESULT`est recommandé pour tous les types interface, car il offre un moyen standard de retourner des erreurs.  
  
|Type d'interface|Description|  
|--------------------|-----------------|  
|Interface double|`HRESULT`. Non modifiable.|  
|Interface personnalisée|`HRESULT`. Non modifiable.|  
|Interface locale personnalisée|Fournir votre propre type de retour, ou sélectionnez dans la liste.|  
|Dispinterface|Fournir votre propre type de retour, ou sélectionnez dans la liste.|  
|Dispinterface du contrôle ActiveX MFC|Si vous implémentez une méthode stock, le type de retour est défini sur la valeur appropriée et n’est pas modifiable. Si vous sélectionnez une méthode dans le **nom de la méthode** liste et cliquez sur **personnalisé** sous **sélectionner le type de la méthode**, sélectionnez un type de retour dans la liste.|  
  
 **Nom de la méthode**  
 Définit le nom de la méthode.  
  
|Type d'interface|Description|  
|--------------------|-----------------|  
|Interface double ATL, interface personnalisée et interface locale personnalisée|Fournissez votre propre nom de la méthode.|  
|Dispinterface MFC|Fournissez votre propre nom de la méthode ou sélectionnez un nom de méthode dans la liste. Si vous sélectionnez un nom dans la liste, la valeur appropriée s’affiche dans le **type de retour** zone et il n’est pas modifiable.|  
|Dispinterface du contrôle ActiveX MFC|Fournissez votre propre ou sélectionnez une des méthodes stocks [DoClick](../mfc/reference/colecontrol-class.md#doclick) et [Actualiser](../mfc/reference/colecontrol-class.md#refresh). Consultez [contrôles ActiveX MFC : ajout de méthodes Stock](../mfc/mfc-activex-controls-adding-stock-methods.md) pour plus d’informations.|  
  
 **Type de méthode**  
 Disponible uniquement pour les contrôles ActiveX MFC. Si vous fournissez un nom de méthode dans le **nom de la méthode** zone, au lieu de sélectionner une méthode dans la liste, cette case n’est pas disponible.  
  
 Si vous sélectionnez une des méthodes dans le **nom de la méthode** , sélectionnez l’implémentation stock ou une implémentation personnalisée.  
  
|Type de méthode|Description|  
|-----------------|-----------------|  
|**Stock**|Valeur par défaut. Insère l’implémentation stock de la méthode que vous sélectionnez dans la **nom de la méthode** liste. **Type de retour** n’est pas modifiable si vous sélectionnez **Stock**.|  
|**Personnalisé**|Insère l’implémentation stub de la méthode sélectionnée dans le **nom de la méthode** liste. Pour les types de méthodes personnalisées, vous pouvez fournir votre propre type de retour, ou vous pouvez sélectionner l’une à partir de la **type de retour** liste.|  
  
 **Nom interne**  
 Disponible pour seulement les méthodes personnalisées ajoutées à une dispinterface MFC. Définit le nom utilisé dans la table de dispatch, le fichier d’en-tête (.h) et le fichier d’implémentation (.cpp). Par défaut, ce nom est identique à **nom de la méthode**. Vous pouvez modifier le nom de la méthode si vous travaillez avec une dispinterface MFC ou si vous ajoutez une méthode personnalisée à une dispinterface de contrôle ActiveX MFC.  
  
|Type d'interface|Description|  
|--------------------|-----------------|  
|Interface double ATL, interface personnalisée et interface locale personnalisée|Non disponible|  
|Dispinterface MFC|Définir le nom de la méthode par défaut. Vous pouvez modifier le nom interne.|  
|Dispinterface du contrôle ActiveX MFC|Vous pouvez définir le nom interne pour les méthodes personnalisées. Méthodes stock n’utilisent pas un nom interne.|  
  
 **Attributs de paramètre**  
 Définit des attributs supplémentaires pour le paramètre spécifié dans **nom de paramètre**.  
  
|Attribut de paramètre|Description|Combinaisons autorisées|  
|-------------------------|-----------------|--------------------------|  
|**In**|Indique que le paramètre est passé à partir de la procédure appelante à la procédure appelée.|**dans** uniquement<br /><br /> **dans** et **out**|  
|**Out**|Indique que le paramètre de pointeur est retourné à partir de la procédure appelée à la procédure appelante (du serveur au client).|**out** uniquement<br /><br /> **dans** et **out**<br /><br /> **out** et **retval**|  
|**Retval**|Indique que le paramètre reçoit la valeur de retour du membre.|**retval** et out|  
  
 **Type de paramètre**  
 Définit le type de données du paramètre. Sélectionnez le type dans la liste.  
  
 **Nom du paramètre**  
 Définit le nom d’un paramètre à passer par votre méthode. Après avoir tapé le nom, vous devez cliquer sur **ajouter** pour l’ajouter à la liste des paramètres qui seront passés via la méthode. Si vous ne fournissez pas un nom de paramètre, l’Assistant ignore tout attribut de paramètre (ATL uniquement) ou **type de paramètre** sélections.  
  
 Une fois que vous cliquez sur **ajouter**, le nom du paramètre s’affiche dans **liste de paramètres**.  
  
 **Remarque** si vous fournissez un nom de paramètre, puis sur **Terminer** avant de cliquer sur **ajouter**, le paramètre n’est pas ajouté à la méthode. Vous devez rechercher la méthode et insérer le paramètre manuellement.  
  
 **Ajouter**  
 Ajoute le paramètre que vous spécifiez dans **nom de paramètre**, ainsi que ses attributs de type et un paramètre pour **liste de paramètres**. Vous devez cliquer sur **ajouter** pour ajouter un paramètre à la liste.  
  
 **Supprimer**  
 Supprime le paramètre que vous sélectionnez dans **liste de paramètres** dans la liste.  
  
 **Liste de paramètres**  
 Affiche tous les paramètres et leurs modificateurs et les types qui sont ajoutés pour la méthode. Lorsque vous ajoutez des paramètres, l’Assistant met à jour **liste de paramètres** pour afficher chaque paramètre avec son modificateur et son type.  
  
## <a name="see-also"></a>Voir aussi  
 [Ajout d’une méthode](../ide/adding-a-method-visual-cpp.md)   
 [Attributs IDL, Assistant Ajout de méthode](../ide/idl-attributes-add-method-wizard.md)