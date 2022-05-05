---
title: 'AMANZI-ATS BCs for Energy'
date: 2022-05-04
permalink: /posts/2013/08/blog-post-2/
tags:
  - cool posts
  - category1
  - category2
---

In this blog, the implementation of swith BCs for energy in AMANZI-ATS will be demonstrated.

Dirichlet_Zero_Gradient
======

src/physics/ats/src/pks/energy/energy_bc_factory.hh
* energy_bc_factory can be used to create the boundary types for energy.
* like "temperature"  "boundary temperature"
** The developer can add the new boundary condition from here.

src/physics/ats/src/pks/energy/energy_base_pk.cc
* #include several .h files, they are used for solving the equation with boundary conditions
* #include :energy_bc_factory.hh" // to create the bc parameters
* #include "energy_base.hh"  //operators and functions, like the martix_adv_
* #

// set up Operator
* bc_temperature_ = bc_factory.CreateTemperature();
* bc_diff_flux_ = bc_factory.CreateDiffusiveFlux();
* bc_flux_ = bc_factory.CreateTotalFlux();
* bc_adv_ = Teuchos::rcp(new Operator::BCs(mesh_, AmanziMesh::FACE, WhetStone::DOF_Type::SCALAR));
 
* // -- create the forward operator for the diffusion term
*   Operators::PDE_DiffusionFactory opfactory;
    matrix_diff_ = opfactory.Create(mfd_plist, mesh_, bc_);
    matrix_diff_->SetTensorCoefficient(Teuchos::null);
    matrix_ = matrix_diff_->global_operator();
* // -- create the forward operator for the advection term
* matrix_adv_ ->SetBCs(bc_adv_, bc_adv_) 

//Evaluate boundary conditions at the current time
  auto& markers = bc_markers();
  auto& values = bc_values();
 
  auto& adv_markers = bc_adv_->bc_model();
  auto& adv_values = bc_adv_->bc_value();

* bc_marker == operator::OPERATOR_BC_NEUMAN 
* bc_adv_ ==operator::OPERATOR_BC_DIRICHLET
* 
src/operators/PDE_Diffusion* 


======

Aren't headings cool?
------
