---
title: "Assistant Ajout de m&#233;thode | Microsoft Docs"
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
  - "vc.codewiz.method.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant Ajout de méthode (C++)"
  - "méthodes (C++), ajouter à l'aide d'Assistants"
ms.assetid: b9a71b0e-9ecf-40fa-9f86-4200cb23d671
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Assistant Ajout de m&#233;thode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez cet Assistant pour ajouter une méthode à une interface.  Selon le type de projet ou le type interface auquel vous ajoutez une méthode, l'Assistant propose différentes options.  
  
## Noms  
 **Type de retour**  
 Type de données retourné par la méthode.  `HRESULT` est recommandé pour tous les types d'interfaces, parce qu'il offre un moyen standard de retourner des erreurs.  
  
|Type d'interface|Description|  
|----------------------|-----------------|  
|Interface double|`HRESULT`.  Non modifiable.|  
|Interface personnalisée|`HRESULT`.  Non modifiable.|  
|Interface locale personnalisée|Indiquez le type de retour de votre choix ou sélectionnez\-en un dans la liste.|  
|Dispinterface|Indiquez le type de retour de votre choix ou sélectionnez\-en un dans la liste.|  
|Dispinterface du contrôle ActiveX MFC|Si vous implémentez une méthode stock, le type de retour est défini sur la valeur appropriée et n'est pas modifiable.  Si vous sélectionnez une méthode dans la liste **Nom de la méthode** et cliquez sur **Personnalisée** sous **Sélectionnez le type de méthode**, sélectionnez un type de retour dans la liste.|  
  
 **Nom de la méthode**  
 Définit le nom de la méthode.  
  
|Type d'interface|Description|  
|----------------------|-----------------|  
|Interface double ATL, interface personnalisée et interface locale personnalisée|Indiquez un nom de méthode de votre choix.|  
|Dispinterface MFC|Indiquez un nom de méthode de votre choix ou sélectionnez\-en un dans la liste.  Si vous sélectionnez un nom dans la liste, la valeur appropriée apparaît dans la zone **Type de retour** et n'est pas modifiable.|  
|Dispinterface du contrôle ActiveX MFC|Indiquez vos propres méthodes stock ou sélectionnez l'une des méthodes [DoClick](../Topic/COleControl::DoClick.md) et [Refresh](../Topic/COleControl::Refresh.md).  Pour plus d'informations, consultez [Contrôles ActiveX MFC : ajout de méthodes stock](../mfc/mfc-activex-controls-adding-stock-methods.md).|  
  
 **Type de méthode**  
 Disponible uniquement pour les contrôles ActiveX MFC.  Si vous indiquez un nom de méthode dans la zone **Nom de la méthode**, au lieu de sélectionner une méthode dans la liste, cette zone n'est pas disponible.  
  
 Si vous sélectionnez une méthode dans la liste **Nom de la méthode**, sélectionnez l'implémentation stock ou une implémentation personnalisée.  
  
|Type de méthode|Description|  
|---------------------|-----------------|  
|**Boursier**|Valeur par défaut.  Insère l'implémentation stock de la méthode sélectionnée dans la liste **Nom de la méthode**.  **Type de retour** n'est pas modifiable si vous sélectionnez **Stock**.|  
|**Personnalisé**|Insère l'implémentation stub de la méthode sélectionnée dans la liste **Nom de la méthode**.  Pour les types de méthodes personnalisées, vous pouvez spécifier le type de retour de votre choix ou en sélectionner un dans la liste **Type de retour**.|  
  
 **Nom interne**  
 Disponible uniquement pour les méthodes personnalisées ajoutées à une dispinterface MFC.  Définit le nom utilisé dans la table de dispatch, le fichier d'en\-tête \(.h\) et le fichier d'implémentation \(.cpp\).  Par défaut, ce nom est identique à celui du **Nom de la méthode**.  Vous pouvez modifier le nom de la méthode si vous utilisez une dispinterface MFC ou si vous ajoutez une méthode personnalisée à une dispinterface de contrôle ActiveX MFC.  
  
|Type d'interface|Description|  
|----------------------|-----------------|  
|Interface double ATL, interface personnalisée et interface locale personnalisée|Non disponible|  
|Dispinterface MFC|Définie sur le nom de la méthode par défaut.  Vous pouvez modifier le nom interne.|  
|Dispinterface du contrôle ActiveX MFC|Vous pouvez définir le nom interne des méthodes personnalisées uniquement.  Les méthodes stock n'utilisent pas de nom interne.|  
  
 **Attributs de paramètres**  
 Définit tout attribut supplémentaire pour le paramètre spécifié dans **Nom du paramètre**.  
  
|Attribut du paramètre|Description|Combinaisons autorisées|  
|---------------------------|-----------------|-----------------------------|  
|**In**|Indique que le paramètre est passé de la procédure appelante à la procédure appelée.|**in** uniquement<br /><br /> **in** et **out**|  
|**Out**|Indique que le paramètre du pointeur est retourné de la procédure appelée à la procédure appelante \(du serveur au client\).|**out** uniquement<br /><br /> **in** et **out**<br /><br /> **out** et **retval**|  
|**Retval**|Indique que le paramètre reçoit la valeur de retour du membre.|**retval** et out|  
  
 **Type de paramètre**  
 Définit le type de données du paramètre.  Sélectionnez le type dans la liste.  
  
 **Nom du paramètre**  
 Définit le nom d'un paramètre à passer par l'intermédiaire de la méthode.  Après avoir tapé le nom, vous devez cliquer sur **Ajouter** pour l'ajouter à la liste de paramètres qui seront passés via la méthode.  En l'absence de nom de paramètre, l'Assistant ignore tout attribut de paramètre \(ATL uniquement\) ou sélection de la zone **Type de paramètre**.  
  
 Lorsque vous cliquez sur **Ajouter**, le nom du paramètre s'affiche dans la **Liste de paramètres**.  
  
 **Remarque** Si vous fournissez un nom de paramètre et si vous cliquez ensuite sur **Terminer** avant d'avoir cliqué sur **Ajouter**, le paramètre n'est pas ajouté à la méthode.  Vous devez rechercher la méthode et insérer le paramètre manuellement.  
  
 **Ajouter**  
 Ajoute le paramètre spécifié dans la zone **Nom du paramètre** ainsi que ses attributs de type et de paramètre dans la zone **Liste de paramètres**.  Pour ajouter un paramètre à la liste, cliquez sur **Ajouter**.  
  
 **Supprimer**  
 Supprime le paramètre que vous sélectionnez de la **Liste de paramètres**.  
  
 **Liste de paramètres**  
 Affiche tous les paramètres, leurs modificateurs et leurs types qui sont ajoutés pour la méthode.  Lors de l'ajout de paramètres, l'Assistant met à jour la **Liste de paramètres** pour afficher chaque paramètre avec son modificateur et son type.  
  
## Voir aussi  
 [Ajout d'une méthode](../ide/adding-a-method-visual-cpp.md)   
 [Attributs IDL, Assistant Ajout de méthode](../ide/idl-attributes-add-method-wizard.md)