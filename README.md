# Angular-Router
#ng generate module app-routing --flat --module=app



import { NgModule } from '@angular/core';
import { CommonModule } from '@angular/common';
import { RouterModule, Routes } from '@angular/router';
import { AuthGuard } from './auth/auth.guard';
import { DashboardComponent } from './dashboard/dashboard.component';
import { LoginComponent } from './login/login.component';
import { PageRoleAssignmentComponent } from './admin/page-role-assignment/page-role-assignment.component';
import { LoginHistoryComponent } from './admin/login-history/login-history.component';
import { IpBasedSecurityComponent } from './admin/ip-based-security/ip-based-security.component';
import { LeadStatusColorComponent } from './admin/lead-status-color/lead-status-color.component';
import { RoleComponent } from './admin/role/role.component';
import { PageNotFoundComponent } from './page-not-found/page-not-found.component';
import { UsersComponent } from './user/users/users.component';
import { BuilderComponent } from './setup/builder/builder.component';
import { CompanyComponent } from './setup/company/company.component';
import { ProjectComponent } from './setup/project/project.component';
import { GlobalUnitTypeComponent } from './setup/global-unit-type/global-unit-type.component';
import { ProjectUnitTypeListComponent } from './setup/project-unit-type-list/project-unit-type-list.component';
const routes: Routes = [
  {
    path: 'home',
    component : DashboardComponent,
    canActivate :[AuthGuard],
    data: {title : "Home"}

  },
  {
    path : 'login',
    component : LoginComponent,
    data: {title : "Login"}
  },
  {
    path : 'role',
    component : RoleComponent,
    canActivate : [AuthGuard],
    data: {title : "Role"}
  },
  {
    path : 'builder',
    component : BuilderComponent, 
    canActivate :[ AuthGuard],
    data: {title : "Builder"}
  },
  {
    path : 'company',
    component : CompanyComponent,
    canActivate : [ AuthGuard ],
    data : {title : "Company"}
  },
  {
    path : 'project',
    component : ProjectComponent,
    canActivate : [ AuthGuard ],
    data : {title : "Project"}
  },
  {
    path : 'global-unit-type',
    component : GlobalUnitTypeComponent,
    canActivate : [ AuthGuard ],
    data : {title : "Global Unit Type"}
  },
  {
    path : 'Project-unit-type',
    component : ProjectUnitTypeListComponent,
    canActivate : [ AuthGuard ],
    data : {title : "Project Unit Type"}
  },
  {
    path : 'page-role-assignment',
    component : PageRoleAssignmentComponent,
    canActivate : [ AuthGuard ],
    data: {title : "Page Role Asignment"}
  },
  {
    path : 'login-history',
    component : LoginHistoryComponent,
    canActivate : [ AuthGuard ],
    data: {title : "Login History"}
  },
  {
    path : 'ip-based-security',
    component : IpBasedSecurityComponent,
    canActivate : [AuthGuard],
    data: {title : "IP Based Security"}
  },
  {
    path : 'lead-status-color',
    component : LeadStatusColorComponent,
    canActivate : [AuthGuard],
    data: {title : "Lead Status Color"}
  },
  {
    path : 'users',
    component : UsersComponent,
    canActivate : [AuthGuard],
    data : { title : 'Users'}
  },
  {
    path : 'page-not-found',
    component : PageNotFoundComponent
  },
   {
    path : '',
    redirectTo : "/home",
    pathMatch : 'full'
  },
  { path : '**', component : PageNotFoundComponent }
]
@NgModule({
  imports: [
    CommonModule,
    RouterModule.forRoot(routes)
  ],
  exports: [RouterModule],
  declarations: []
})
export class AppRoutingModule { }
