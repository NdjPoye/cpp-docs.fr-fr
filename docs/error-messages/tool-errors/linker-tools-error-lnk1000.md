---
title: "LNK1000 d’erreur des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1000
dev_langs:
- C++
helpviewer_keywords:
- LNK1000
ms.assetid: 86421b9a-460a-4285-8dce-9b8257d78122
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e3733fb40165c07e9f8c28c723aa0c645740040f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1000"></a>Erreur des outils Éditeur de liens LNK1000
Erreur inconnue ; consultez la documentation pour les options de support technique  
  
 Notez les circonstances de l’erreur, essayez d’isoler le problème et de créer un cas de test reproductible, puis contactez `Microsoft Product Support Services`. Pour plus d’informations sur la façon d’examiner et de signaler ces erreurs, consultez [http://support.microsoft.com/default.aspx?scid=kb;en-us;134650](http://support.microsoft.com/default.aspx?scid=kb;en-us;134650).  
  
 Vous pouvez obtenir cette erreur si vous combinez des fichiers d’en-tête standard (par exemple, dos.h) et vos propres fichiers. `#include`les en-têtes standard en premier lieu, suivi par vos propres fichiers d’en-tête.