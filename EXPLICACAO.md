1. pox.xml:
    Em resumo, acrescenta um módulo de segurança (Spring Security), JWT para autenticação e validação de dados.

    - dependências de segurança e autenticação - (adicionada a parte de autenticação):  habilita o Spring Security, framework de autenticação/autorização no Spring Boot 
    - dependências para JWT (JSON Web Token) - não tinha: permitem criar, assinar e validar tokens JWT, usados geralmente para autenticação sem estado (stateless), típica em APIs REST
    - validação de dados (adicionado): Fornece Bean Validation (Jakarta Validation) com anotações como @NotNull, @Email, @Size, etc. Muito útil para validar DTOs em requisições.

2. cors.config:
    Configuração mais flexível para desenvolvimento, permitindo todas as origens sem credenciais, mas já traz exemplos comentados para usar em produção.

    - Credenciais (AllowCredentials): false - Bloqueia credenciais, mas em compensação permite abrir o CORS para todas as origens sem restrição. 
    - Origem permitida: Aceita todas as origens (*). Isso é útil em desenvolvimento, mas em produção pode ser um risco de segurança.
    - Comentários sobre uso em produção: traz um guia no código

3. datainitializer: 
    Inclui também dados de segurança/autenticação (usuários e senhas padrão).

    - Usuários padrão: cria usuários padrão no banco/Isso é feito com o método criarUsuariosPadrao(), que usa UsuarioRepository e PasswordEncoder.

        admin / admin123 (Administrador)
        user / user123 (Usuário comum)

    - Injeções adicionais: Necessários para criar e salvar os usuários com senha criptografada. 
        @Autowired
        private UsuarioRepository usuarioRepository;
        @Autowired
        private PasswordEncoder passwordEncoder;
    - Senha criptografada: Garante que a senha não fica em texto puro no banco (fundamental para segurança).
    - Fluxo de execução: ria os usuários padrão (se não existirem). Depois segue o mesmo processo de inicializar robôs, eventos e entregas.
4. application.properties:

    - Duplicação removível: consolidou as configurações (H2, JPA e server port) em apenas um bloco, evitando redundância.
    - Adição de autenticação JWT: adicionadas as propriedades para JWT, permite gerar e validar tokens JWT para autenticação e controle de acesso na aplicação.


