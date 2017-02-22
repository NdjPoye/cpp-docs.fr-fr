---
title: "Mise &#224; jour de donn&#233;es avec le contr&#244;le RemoteData RDO | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RemoteData (contrôle RDO)"
  - "RemoteData (contrôle RDO), mise à jour de données"
  - "RemoteData (contrôle)"
  - "RemoteData (contrôle), mise à jour de données"
ms.assetid: abb4175f-612e-4645-905e-c0fa918b0fd7
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Mise &#224; jour de donn&#233;es avec le contr&#244;le RemoteData RDO
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les données du contrôle RemoteData RDO peuvent être en lecture seule ou modifiables.  
  
### Pour créer une application qui modifie les données à l'aide du contrôle RemoteData RDO  
  
1.  Définissez la propriété **CursorDriver** du contrôle RemoteData RDO.  
  
    -   Les curseurs de type Server Side \(côté serveur\) stockent les données retournées sur le serveur.  
  
    -   Les curseurs de type Client Side \(côté client\) ODBC stockent les données dans la mémoire locale du client.  
  
    -   Les curseurs de type Client Batch Side \(côté batch client\) utilisent une bibliothèque de curseurs conçue pour traiter les problèmes liés à l'accès concurrentiel.  
  
    -   L'option No Cursor est utilisée quand une requête d'action est exécutée et qu'aucun curseur n'est donc nécessaire.  
  
2.  Définissez la propriété **LockType** du contrôle RemoteData RDO.  L'accès concurrentiel optimiste reposant sur l'option resultset est recommandé.  
  
    -   L'accès concurrentiel en lecture seule ne doit pas être utilisé si vous souhaitez que les données soient modifiables.  
  
    -   L'accès concurrentiel pessimiste verrouille les données pendant la mise à jour de sorte qu'aucun autre utilisateur ne puisse se trouver en position d'effectuer des modifications de données incompatibles.  
  
    -   L'accès concurrentiel optimiste ne verrouille pas les données, mais s'il détecte pendant l'enregistrement qu'un autre client a publié un état incompatible, le contrôle RemoteData RDO signale une erreur.  
  
3.  Définissez la propriété **ResultsetType** du contrôle RemoteData RDO.  Assurez\-vous que le pilote ODBC prend en charge les options sélectionnées :  
  
    -   Quand l'option Create Static Cursor est sélectionnée, les modifications ne sont détectées qu'une fois que le curseur a été fermé, puis rouvert.  
  
    -   Quand l'option Create Keyset Cursor est sélectionnée, le curseur permet des insertions, des mises à jour et des suppressions dans le curseur Keyset même.  
  
4.  Définissez le contrôle lié aux données en tenant compte des possibilités de mise à jour.  Remarquez que certains contrôles ne permettent pas la mise à jour.  
  
 Pour plus d'informations sur l'utilisation de ces objets, consultez la documentation sur le contrôle RemoteData RDO.  
  
## Voir aussi  
 [Liaison de données RDO](../../data/ado-rdo/rdo-databinding.md)   
 [Utilisation de la liaison de données RDO dans Visual C\+\+](../../data/ado-rdo/using-rdo-databinding-in-visual-cpp.md)