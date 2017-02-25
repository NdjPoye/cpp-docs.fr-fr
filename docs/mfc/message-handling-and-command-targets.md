---
title: "Gestion des messages et cibles des commandes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IOleCommandTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "routage des commandes, cibles de la commande"
  - "cibles de la commande"
  - "interface IOleCommandTarget"
  - "gestion des messages, documents actifs"
ms.assetid: e45ce14c-e6b6-4262-8f3b-4e891e0ec2a3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Gestion des messages et cibles des commandes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'interface de commande de dispatch `IOleCommandTarget` définit un mécanisme simple et extensible pour interroger et exécuter des commandes.  Ce mécanisme est plus simple que `IDispatch` de l'automation car elle dépend entièrement d'un ensemble standard de commandes ; les commandes ont rarement des arguments, et aucune information de type n'est requise \(la cohérence des types est également diminuée pour les arguments de commande\).  
  
 Dans la création de l'interface de dispatch de commande, chaque commande appartient à un groupe « sales » qui lui\-même est identifiée par **GUID**.  Par conséquent, toute personne peut définir un nouveau groupe et définir toutes les commandes au sein de ce groupe sans avoir à se coordonner avec Microsoft ou tout autre fournisseur. \(Il s'agit essentiellement du même moyen que la définition de **dispinterface** plus **dispIDs** dans l'automation.  Il existe des chevauchements ici, bien que ce mécanisme de routage des commandes soit uniquement fait pour le routage des commandes et pas pour le script et la programmation à grande échelle comme handles automation.\)  
  
 `IOleCommandTarget` prend en charge les scénarios suivants :  
  
-   Lorsqu'un objet est activé sur place, seules les barres d'outils de l'objet sont généralement affichées et les barres d'outils de l'objet peuvent avoir des boutons pour certaines commandes de conteneur comme **Print**, **Print Aperçu**, **Enregistrer**, `New`, **Zoom**, entre autres. \(Les normes d'activation sur place recommandent de supprimer les objets de ces boutons, des barres d'outils, soit au moins des désactivez.  Cette conception autorise ces commandes à être activé et routé au bon gestionnaire.\) Actuellement, il n'existe aucun mécanisme pour l'objet pour distribuer les commandes au conteneur.  
  
-   Lorsqu'un document actif est incorporé dans un conteneur de documents actifs \(tel que le classeur Office\), le conteneur peut être amené à envoyer des commandes comme **Print**, **Page Installation**, **Propriétés**, et d'autres au document actif contenu.  
  
 Le routage des commandes simple peut être géré via les normes existants et le standard de l'automation `IDispatch`.  Toutefois, la surcharge impliquée dans `IDispatch` est supérieure à ce qui est requis ici, ce `IOleCommandTarget` fournit un moyen plus simple d'atteindre les mêmes objectifs :  
  
 `interface IOleCommandTarget : IUnknown`  
  
 `{`  
  
 `HRESULT QueryStatus(`  
  
 `[in] GUID *pguidCmdGroup,`  
  
 `[in] ULONG cCmds,`  
  
 `[in,out][size_is(cCmds)] OLECMD *prgCmds,`  
  
 `[in,out] OLECMDTEXT *pCmdText);`  
  
 `HRESULT Exec(`  
  
 `[in] GUID *pguidCmdGroup,`  
  
 `[in] DWORD nCmdID,`  
  
 `[in] DWORD nCmdExecOpt,`  
  
 `[in] VARIANTARG *pvaIn,`  
  
 `[in,out] VARIANTARG *pvaOut);`  
  
 `}`  
  
 La méthode d'`QueryStatus` ici teste si un jeu de commandes, la valeur identifiée par **GUID**, est pris en charge.  Cet appel remplit un tableau de valeurs d'**OLECMD** \(structures\) avec la liste des commandes prise en charge et retourne le texte qui décrit le nom d'une commande et\/ou des informations d'état.  Lorsque l'appelant souhaite appeler une commande, il peut transmettre la commande \(et le **GUID**set\) à **Exec** avec les options et les arguments, l'obtention de la valeur de retour.  
  
## Voir aussi  
 [Conteneurs de documents actifs](../mfc/active-document-containers.md)