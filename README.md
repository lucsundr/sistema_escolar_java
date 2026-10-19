Erro 1: `Professor.java` - diferente dos outros modelos, ele não usa `@GeneratedValue(strategy = GenerationType.IDENTITY)` no id, e com isso ele não define o ID<br>
Erro 2: `Aluno.java` - ao inves de usar o valor do RA, ele recebe o falor do curso novamente, o certo sendo  `this.ra = dados.ra();`<br>
Erro 3: `ProfessorController.java` - O RequestMapping usa "/professor", mas no Professor.java o nome correto e "professores" no plural<br>
Erro 4: `pom.xml` - a dependência do H2 usa `<scope>test</scope>`, trocando isso para `<scope>runtime</scope>`<br>
Erro 5: `application-test.properties` - ele usa `spring.jpa.hibernate.ddl-auto`, que impede a criação automatica de tabelas, e com isso foi removida<br>
Erro 6: `AlunoController.java` - O metodo de atualizar altera a entidade mas não usa `@Transactional`. basta coloca-lo em baixo do `@PutMapping` <br>
Erro 7: `Matricula.java` - No campo aluno, ele usa `@OneToOne`, representando uma matrícula para cada aluno. Para corrigir, basta trocar para `@ManyToOne` <br>
Erro 8: `DadosCadastroMatricula.java` e `MatriculaController.java` - Ambos usam "idAluno", mas o correto no código e "alunoId".<br>