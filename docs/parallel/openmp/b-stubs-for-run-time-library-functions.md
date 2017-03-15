---
title: "B. Stubs for Run-time Library Functions | Microsoft Docs"
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
ms.assetid: fdfdabe0-f678-4551-80d5-827b62354427
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# B. Stubs for Run-time Library Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette section fournit des stubs pour les fonctions des bibliothèques Runtime définies dans l'API d'OpenMP C et C\+\+.  Les stubs sont fournis pour activer la portabilité aux plateformes qui ne prennent pas en charge l'API d'OpenMP C et C\+\+.  Sur ces plateformes, les programmes d'OpenMP doivent être liés à une bibliothèque contenant ces fonctions stub.  les fonctions de stub supposent que les directives dans le programme d'OpenMP sont ignorées.  Fondamentalement, ils émulent la sémantique série.  
  
> [!NOTE]
>  La variable de verrou qui apparaît dans les fonctions de verrou doit être accessible exclusivement par ces fonctions.  Il ne doit pas être initialisé ou sinon modifié dans le programme utilisateur.  Les utilisateurs ne doivent pas faire des hypothèses sur les mécanismes utilisés par OpenMP C et les implémentations C\+\+ pour implémenter des verrous sur le schéma utilisée par le stub s'exécute.  
  
### Code  
  
```  
#include <stdio.h>  
#include <stdlib.h>  
#include "omp.h"  
#ifdef __cplusplus  
extern "C" {  
#endif  
  
void omp_set_num_threads(int num_threads)  
{  
}  
int omp_get_num_threads(void)  
{  
    return 1;  
}  
int omp_get_max_threads(void)  
{  
    return 1;  
}  
int omp_get_thread_num(void)  
{  
    return 0;  
}  
int omp_get_num_procs(void)  
{  
    return 1;  
}  
void omp_set_dynamic(int dynamic_threads)  
{  
}  
int omp_get_dynamic(void)  
{  
    return 0;  
}  
int omp_in_parallel(void)  
{  
    return 0;  
}  
void omp_set_nested(int nested)  
{  
}  
int omp_get_nested(void)  
{  
    return 0;  
}  
enum {UNLOCKED = -1, INIT, LOCKED};  
void omp_init_lock(omp_lock_t *lock)  
{  
    *lock = UNLOCKED;  
}  
void omp_destroy_lock(omp_lock_t *lock)  
{  
    *lock = INIT;  
}  
void omp_set_lock(omp_lock_t *lock)  
{  
    if (*lock == UNLOCKED)   
    {  
        *lock = LOCKED;  
    }   
    else   
        if (*lock == LOCKED)   
        {  
         fprintf_s(stderr, "error: deadlock in using lock variable\n");  
         exit(1);  
        } else {  
         fprintf_s(stderr, "error: lock not initialized\n");  
         exit(1);  
        }  
}  
  
void omp_unset_lock(omp_lock_t *lock)  
{  
    if (*lock == LOCKED)   
    {  
        *lock = UNLOCKED;  
    }   
    else   
        if (*lock == UNLOCKED)   
        {  
            fprintf_s(stderr, "error: lock not set\n");  
            exit(1);  
        } else {  
            fprintf_s(stderr, "error: lock not initialized\n");  
            exit(1);  
        }  
}  
  
int omp_test_lock(omp_lock_t *lock)  
{  
    if (*lock == UNLOCKED)   
    {  
        *lock = LOCKED;  
        return 1;  
    } else if (*lock == LOCKED) {  
        return 0;  
    } else {  
        fprintf_s(stderr, "error: lock not initialized\n");  
        exit(1);  
    }  
}  
  
#ifndef OMP_NEST_LOCK_T  
typedef struct {  // This really belongs in omp.h   
    int owner;  
    int count;  
} omp_nest_lock_t;  
#endif  
enum {MASTER = 0};  
void omp_init_nest_lock(omp_nest_lock_t *lock)  
{  
    lock->owner = UNLOCKED;  
    lock->count = 0;  
}  
void omp_destroy_nest_lock(omp_nest_lock_t *lock)  
{  
    lock->owner = UNLOCKED;  
    lock->count = UNLOCKED;  
}  
  
void omp_set_nest_lock(omp_nest_lock_t *lock)  
{  
    if (lock->owner == MASTER && lock->count >= 1)   
    {  
        lock->count++;  
    } else   
        if (lock->owner == UNLOCKED && lock->count == 0)   
        {  
            lock->owner = MASTER;  
            lock->count = 1;  
        } else   
        {  
       fprintf_s(stderr, "error: lock corrupted or not initialized\n");  
         exit(1);  
    }  
}  
  
void omp_unset_nest_lock(omp_nest_lock_t *lock)  
{  
    if (lock->owner == MASTER && lock->count >= 1)   
    {  
        lock->count--;  
        if (lock->count == 0)   
        {  
            lock->owner = UNLOCKED;  
        }  
    } else   
        if (lock->owner == UNLOCKED && lock->count == 0)   
        {  
            fprintf_s(stderr, "error: lock not set\n");  
            exit(1);  
        } else   
        {  
       fprintf_s(stderr, "error: lock corrupted or not initialized\n");  
       exit(1);  
    }  
}  
  
int omp_test_nest_lock(omp_nest_lock_t *lock)  
{  
    omp_set_nest_lock(lock);  
    return lock->count;  
}  
  
double omp_get_wtime(void)  
{  
    // This function does not provide a working  
    // wallclock timer. Replace it with a version  
    // customized for the target machine.  
    return 0.0;  
}  
  
double omp_get_wtick(void)  
{  
    // This function does not provide a working  
    // clock tick function. Replace it with  
    // a version customized for the target machine.  
    return 365. * 86400.;  
}  
  
#ifdef __cplusplus  
}  
#endif  
```