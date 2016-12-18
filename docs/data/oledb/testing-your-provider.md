---
title: "Test de votre fournisseur | Microsoft Docs"
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
  - "fournisseurs OLE DB, tester"
  - "tester les fournisseurs"
  - "tester, fournisseurs OLE DB"
ms.assetid: bf824fe4-81af-4ffb-beb3-4fa2928dc450
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Test de votre fournisseur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Avant de diffuser un fournisseur, vous devez effectuer les tests ci\-après, dans l'ordre indiqué.  Ces tests permettent de garantir le bon fonctionnement du fournisseur pour la plupart des utilisateurs potentiels.  
  
1.  Testez le fournisseur en utilisant une application [consommateur](../../data/oledb/creating-an-ole-db-consumer.md) écrite à l'aide des modèles du consommateur OLE DB.  Le consommateur de test doit couvrir tous les domaines fonctionnels de votre fournisseur \(tout le code que vous avez ajouté ou modifié\).  
  
2.  Testez le fournisseur en utilisant une application consommateur écrite à l'aide d'ADO.  La plupart des développeurs \(notamment les développeurs Microsoft Visual Basic et Microsoft C\#\) utilisent ADO or ADO.NET pour les applications consommateurs.  Le consommateur de test doit couvrir tous les domaines fonctionnels de votre fournisseur.  Pour obtenir un exemple d'application consommateur ADO, consultez [Exemples de code ADO dans Microsoft Visual Basic](https://msdn.microsoft.com/en-us/library/ms807514.aspx).  
  
3.  Exécutez les tests de compatibilité OLE DB \(notamment les tests de compatibilité ADO\) pour vérifier que votre fournisseur est conforme au standard de niveau 0 pour les fournisseurs OLE DB. \(Pour ne explication de niveau 0, recherchez « Tests de conformité du niveau 0 OLE DB » dans [Le guide de référence du programmeur OLE DB](http://go.microsoft.com/fwlink/?LinkId=121548).  Ces tests et la documentation associée sont fournis avec Visual C\+\+ dans le Kit de développement Data Access SDK.  Ces tests vous aident aussi à vous assurer que votre fournisseur s'exécute correctement lorsqu'il est regroupé avec d'autres [fournisseurs de services](../../data/oledb/ole-db-resource-pooling-and-services.md) et qu'ils sont particulièrement utiles si vous modifiez ou ajoutez des propriétés.  Pour plus d'informations sur les tests de compatibilité, consultez le fichier Readme pour le Kit de développement Data Access SDK, qui se trouve sur l'un des CD\-ROM de Visual Studio.  
  
## Voir aussi  
 [Utilisation des modèles du fournisseur OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)