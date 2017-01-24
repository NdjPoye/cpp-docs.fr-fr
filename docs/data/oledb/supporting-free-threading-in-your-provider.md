---
title: "Prise en charge du Free Threading dans votre fournisseur | Microsoft Docs"
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
  - "fournisseurs OLE DB, multithread"
  - "threads (C++), fournisseurs"
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Prise en charge du Free Threading dans votre fournisseur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Toutes les classes du fournisseur OLE DB sont thread\-safe, et les entrées de la base de registres sont définies en conséquence.  Il est judicieux de prendre en charge le mode Free Threading pour améliorer les performances dans les situations multi\-utilisateur.  Pour aider à conserver un fournisseur thread safe, vous devez vous assurer que votre code est bloqué correctement.  Chaque fois que vous écrivez ou stockez des données, vous devez bloquer l'accès à ces données au moyen de sections critiques.  
  
 Chaque objet des modèles du fournisseur OLE DB possède sa propre section critique.  Pour faciliter le blocage, chaque nouvelle classe que vous créez doit être une classe de modèle qui prend le nom de la classe parente en tant qu'argument.  
  
 L'exemple suivant montre comment bloquer le code :  
  
```  
template <class T>  
class CMyObject<T> : public...  
  
HRESULT MyObject::MyMethod(void)  
{  
   T* pT = (T*)this;      // this gets the parent class   
  
// You don't need to do anything if you are only reading information  
  
// If you want to write information, do the following:  
   pT->Lock();         // engages critical section in the object  
   ...;                // write whatever information you wish  
   pT->Unlock();       // disengages the critical section  
}  
```  
  
 Pour plus d'informations sur la manière de protéger les sections critiques avec `Lock` et `Unlock`, consultez [Multithreading : comment utiliser les classes de synchronisation](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
 Vous devez également vous assurer que les méthodes que vous substituez \(`Execute`, par exemple\) sont thread\-safe.  
  
## Voir aussi  
 [Utilisation des modèles du fournisseur OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)