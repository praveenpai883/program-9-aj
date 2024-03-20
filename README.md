<!doctype html>
<html ng-app>
 <head>
 <script
src="https://ajax.googleapis.com/ajax/libs/angularjs/1.3.3/angular.min.js"></script>
 </head>
 <body>
 <div>
 <div ng-app="myApp">
 <div ng-controller="EmployeeController">
 <h1>Employee List</h1>
 <input type="text" ng-model="searchName" placeholder="Search by name">
 <input type="number" ng-model="searchSalary" placeholder="Search by salary">
 <button ng-click="searchEmployees()">Search</button>
 <ul>
 <li ng-repeat="employee in employees">{{employee.name}} - {{employee.salary}}</li>
 </ul>
 </div>
</div>
<script src= “ Program9.js”></script>
 </body>
</html>
Program9.js
var myApp = angular.module('myApp', []);
myApp.controller('EmployeeController', function($scope) {
 $scope.employees = [
 { name: 'John Doe', salary: 50000 },
 { name: 'Jane Doe', salary: 60000 },
 { name: 'Peter Parker', salary: 70000 },
 { name: 'Mary Jane Watson', salary: 80000 }
 ];
 $scope.searchEmployees = function() {
 $scope.employees = $scope.employees.filter(function(employee) {
 return employee.name.toLowerCase().indexOf($scope.searchName.toLowerCase()) !== -
1 && employee.salary >= $scope.searchSalary;
 });
 };
});
