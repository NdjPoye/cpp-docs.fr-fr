---
title: file_status, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- filesystem/std::experimental::filesystem::file_status
- filesystem/std::experimental::filesystem::file_status::operator=
- filesystem/std::experimental::filesystem::file_status::type
- filesystem/std::experimental::filesystem::file_status::permissions
dev_langs: C++
ms.assetid: 9781840e-ad22-44dd-ad79-0fabaa94bac4
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::experimental::filesystem::file_status
- std::experimental::filesystem::file_status::operator=
- std::experimental::filesystem::file_status::type
- std::experimental::filesystem::file_status::permissions
ms.workload: cplusplus
ms.openlocfilehash: f76bbbe5c11b5fbd7a7e9cc7ed6a4f9851805f29
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="filestatus-class"></a>file_status, classe
Encapsule un [file_type](../standard-library/filesystem-enumerations.md#file_type) et des [perms](../standard-library/filesystem-enumerations.md#perms) de fichier.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
class file_status;  
```  
  
## <a name="filestatusfilestatus"></a>file_status::file_status  
  
```cpp  
explicit file_status(  
   file_type ftype = file_type::none,  
   perms mask = perms::unknown) noexcept;  
  
file_status(const file_status&) noexcept = default;  
  
file_status(file_status&&) noexcept = default; 

~file_status() noexcept = default; 
```  
  
## <a name="filestatusoperator"></a>file_status::operator=  
  
```cpp  
file_status& operator=(const file_status&) noexcept = default;  
file_status& operator=(file_status&&) nexcept = default;  
```  
  
 Les opérateurs d’affectation de membre par défaut se comportent comme prévu.  
  
## <a name="type"></a>type  
  
```cpp  
file_type type() const noexcept  
void type(file_type ftype) noexcept  
```  
  
 Obtient ou définit le file_type.  
  
## <a name="permissions"></a>permissions  
  
```cpp  
perms permissions() const noexcept  
void permissions(perms mask) noexcept   
```  
  
 Obtient ou définit les autorisations de fichiers.  
  
 Utilisez l’accesseur Set pour rendre un fichier accessible en lecture seule ou pour supprimer l’attribut de lecture seule.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<filesystem >  
  
 **Namespace :** std::experimental::filesystem, std::experimental::filesystem  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Path, classe](../standard-library/path-class.md)   
 [\<filesystem>](../standard-library/filesystem.md)

