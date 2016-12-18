---
title: "Prise en charge des transactions dans OLE&#160;DB | Microsoft Docs"
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
  - "bases de données (C++), transactions"
  - "transactions distribuées (C++)"
  - "transactions imbriquées (C++)"
  - "OLE DB (C++), prise en charge des transactions"
  - "OLE DB (modèles du consommateur) (C++), prise en charge des transactions"
  - "transactions (C++), prise en charge OLE DB pour"
ms.assetid: 3d72e583-ad38-42ff-8f11-e2166d60a5a7
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Prise en charge des transactions dans OLE&#160;DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une [transaction](../../data/transactions-mfc-data-access.md) est une façon de regrouper, ou de mettre en lot, une série d'opérations de mise à jour d'une source de données de manière à ce qu'elles réussissent toutes et soient toutes validées en même temps ou \(si l'une d'elles échoue\) qu'aucune d'elles ne soit validée et que la transaction entière soit restaurée.  Ce processus assure l'intégrité du résultat sur la source de données.  
  
 OLE DB prend en charge les transactions à l'aide des trois méthodes suivantes :  
  
-   [\<caps:sentence id\="tgt4" sentenceid\="0699a86bb6d6316bff035b804a56f0aa" class\="tgtSentence"\>ITransactionLocal::StartTransaction\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms709786.aspx)  
  
-   [\<caps:sentence id\="tgt5" sentenceid\="39299b0fea086b86052550bd165334f7" class\="tgtSentence"\>ITransaction::Commit\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms713008.aspx)  
  
-   [\<caps:sentence id\="tgt6" sentenceid\="8e992150c28ae247d532408ca7828bfe" class\="tgtSentence"\>ITransaction::Abort\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms709833.aspx)  
  
## Relations des sessions et des transactions  
 Un objet source de données unique peut créer un ou plusieurs objets session, dont chacun peut se situer à l'intérieur ou à l'extérieur de la portée d'une transaction à un moment donné.  
  
 Quand une session n'entre pas une transaction, tout le travail effectué au cours de cette session sur le magasin de données est immédiatement validé à chaque appel de méthode. \(C'est ce qu'on appelle parfois le mode de validation automatique ou mode implicite.\)  
  
 Quand une session entre une transaction, tout le travail effectué au cours de la session sur le magasin de données fait partie de cette transaction et est validé ou abandonné selon le concept du tout ou rien. \(C'est ce qu'on appelle parfois le mode de validation manuelle.\)  
  
 La prise en charge des transactions est propre au fournisseur.  Si le fournisseur que vous utilisez prend en charge les transactions, un objet session qui prend en charge **ITransaction** et **ITransactionLocal** peut entrer une transaction simple \(c'est\-à\-dire, non imbriquée\).  La classe des modèles OLE DB [CSession](../../data/oledb/csession-class.md) prend en charge ces interfaces et représente le mode recommandé pour implémenter la prise en charge des transactions dans Visual C\+\+.  
  
## Démarrage et arrêt de la transaction  
 Vous appelez les méthodes `StartTransaction`, **Commit** et **Abort** au sein de l'objet jeu de lignes dans le consommateur.  
  
 L'appel de **ITransactionLocal::StartTransaction** démarre une nouvelle transaction locale.  Lorsque vous démarrez la transaction, les modifications éventuellement mandatées par les opérations suivantes ne sont pas appliquées en fait tant que vous n'aurez pas validé la transaction.  
  
 L'appel de **ITransaction::Commit** ou de **ITransaction::Abort** met fin à la transaction.  **Commit** déclenche l'application de toutes les modifications relevant de la portée de la transaction dans le magasin de données.  **Abort** entraîne l'annulation de toutes les modifications situées dans la portée de la transaction, et le magasin de données est laissé dans l'état où il se trouvait avant le début de la transaction.  
  
## Transactions imbriquées  
 Une [transaction imbriquée](https://msdn.microsoft.com/en-us/library/ms716985.aspx) se produit lorsque vous commencez une nouvelle transaction locale alors qu'une transaction active existe déjà dans la session.  La nouvelle transaction démarre en tant que transaction imbriquée sous la transaction en cours.  Si le fournisseur ne prend pas en charge les transactions imbriquées, l'appel de `StartTransaction` quand une transaction est déjà active dans la session retourne **XACT\_E\_XTIONEXISTS**.  
  
## Transactions distribuées  
 Une transaction distribuée est une transaction qui met à jour les données distribuées, c'est\-à\-dire les données contenues sur plusieurs systèmes informatiques mis en réseau.  Si vous souhaitez prendre en charge les transactions sur un système distribué, vous devez utiliser le .NET Framework au lieu de prendre en charge des transactions OLE DB.  
  
## Voir aussi  
 [Utilisation des accesseurs](../../data/oledb/using-accessors.md)