## API Document

### License

这段是使用协议，我用中文写在前面，希望大家明白我意思。

The MIT License (MIT)

Copyright (c) 2015 TakWolf

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

### Overview

This is a proxy of Liaoning Technical University Education Administration System.

### Principle

This proxy just like a spider, when you get info from this system, our proxy server simulate your login, analyze the important information, and finally return to you.

**WARMING: We don't collect your imformation, when you change your password the proxy would't work**

### Useage

Our API obey RESTful Standard strictly.

#### ROOT URL

`http://api.online.lntu.org/`

#### Login

* Method: POST
* URI: account/login
* param: 

<table><thead>
<tr>
<th> param name </th>
<th> not null </th>
<th> class </th>
<th> remarks </th>
</thead><tbody>
</tr>
<tr>
<td> userId </td>
<td> yes </td>
<td> string </td>
<td></td>
</tr>
<tr>
<td> password </td>
<td> yes </td>
<td> string </td>
<td></td>
</tr>
</tbody></table>

* return

<table><thead>
<tr>
<th> param name </th>
<th> class </th>
<th> remarks </th>
</thead><tbody>
</tr>
<tr>
<td> userId </td>
<td> string </td>
<td></td>
</tr>
<tr>
<td> loginToken </td>
<td> string </td>
<td> save it safely, will be used next </td>
</tr>
<tr>
<td> expiresAt </td>
<td> datetime </td>
<td> ISO 8601 format</td>
</tr>
<tr>
<td> userType </td>
<td> string </td>
<td> STUDENT / ADMIN / TEACHER </td>
</tr>
</tbody></table>

* error: You can test by yourself

#### Self Imformation

* Header: Key: "Authorization", Value: loginToken
* Method: GET
* URI: student/~self
* param: nil
* return: [Student](model/student)
* error: You can test by yourself

#### Class Table

* Header: Key: "Authorization", Value: loginToken
* Method: GET
* URI: class-table/~self
* param:

<table><thead>
<tr>
<th> param name </th>
<th> not null </th>
<th> class </th>
<th> remarks </th>
</thead><tbody>
</tr>
<tr>
<td> year </td>
<td> yes </td>
<td> string </td>
<td> 2014 / 2015 and so on </td>
</tr>
<tr>
<td> term </td>
<td> yes </td>
<td> string </td>
<td> 春 / 秋 </td>
</tr>
</tbody></table>

* return: [Try by yourself](#)
* error: You can test by yourself

#### Unpass Course

* Header: Key: "Authorization", Value: loginToken
* Method: GET
* URI: unpass-course/~self
* param: nil
* return: [Unpass](model/unpass)
* error: You can test by yourself

#### Grades

* Header: Key: "Authorization", Value: loginToken
* Method: GET
* URI: grades/~self
* param: nil
* return: [Grades](model/grade)
* error: You can test by yourself
* remarks: it includes your average credit

#### Exam Plan

* Header: Key: "Authorization", Value: loginToken
* Method: GET
* URI: exam-plan/~self
* param: nil
* return: [Plan](model/plan)
* error: You can test by yourself

#### Skill Test Score

* Header: Key: "Authorization", Value: loginToken
* Method: GET
* URI: skill-test-score/~self
* param: nil
* return: [Skill Test](model/skill)
* error: You can test by yourself