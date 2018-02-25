---
title: filesystem_error, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::filesystem_error
dev_langs:
- C++
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 764be5467282b04e4cd7fa13ee44fddee7c0a51b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="filesystemerror-class"></a>filesystem_error, classe
Classe de base pour toutes les exceptions qui sont levées pour signaler un dépassement de capacité du système de bas niveau.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class filesystem_error    : public system_error;  
```  
  
## <a name="remarks"></a>Notes  
 La classe sert de classe de base pour toutes les exceptions levées afin de signaler une erreur dans des fonctions \<filesystem>. Elle stocke un objet de type chaîne, appelé ici mymesg. Il stocke également les deux objets de type path, appelés mypval1 et mypval2.  
  
## <a name="filesystemerrorfilesystemerror"></a>filesystem_error::filesystem_error  
  
```  
filesystem_error(const string& what_arg,
    error_code ec);

filesystem_error(const string& what_arg,  
    const path& pval1,
    error_code ec);

filesystem_error(const string& what_arg,  
    const path& pval1,
    const path& pval2,
    error_code ec);
```  
  
 Le premier constructeur construit son message à partir de what_arg et ec. Le deuxième constructeur construit également son message à partir de pval1, qu’il stocke dans mypval1. Le troisième constructeur construit également son message à partir de pval1, qu’il stocke dans mypval1, et à partir de pval2, qu’il stocke dans mypval2.  
  
## <a name="filesystemerrorpath1"></a>filesystem_error::path1  
  
```  
const path& path1() const noexcept;  
```  
  
 La fonction membre retourne mypval1.  
  
## <a name="filesystemerrorpath2"></a>filesystem_error::path2  
  
```  
const path& path2() const noexcept;  
```  
  
 La fonction membre retourne mypval2.  
  
## <a name="filesystemerrorwhat"></a>filesystem_error::what  
  
```  
const char *what() const noexcept;  
```  
  
 La fonction membre retourne un pointeur vers un NTBS, de préférence, composé à partir de runtime_error::what(), system_error::what(), mymesg, mypval1.native_string(), and mypval2.native_string().  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<filesystem >  
  
 **Espace de noms :** std::experimental::filesystem  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [system_error, classe](../standard-library/system-error-class.md)   
 [\<filesystem>](../standard-library/filesystem.md)   
 [\<exception>](../standard-library/exception.md)

