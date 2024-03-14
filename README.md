# Formulario-simple
import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class Formulario extends JFrame implements ActionListener {
    // Componentes del formulario
    private JLabel lblEmail, lblPassword, lblConfirmPassword, lblUsername;
    private JTextField txtEmail, txtUsername;
    private JPasswordField txtPassword, txtConfirmPassword;
    private JButton btnForgotPassword, btnLoginWithGoogle, btnSubmit;

    public Formulario() {
        setTitle("Formulario de Registro");
        setSize(400, 300);
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        setLayout(new GridLayout(5, 2, 5, 5));

        // Inicializar componentes
        lblEmail = new JLabel("Correo electrónico:");
        txtEmail = new JTextField();
        lblPassword = new JLabel("Contraseña:");
        txtPassword = new JPasswordField();
        lblConfirmPassword = new JLabel("Verificar contraseña:");
        txtConfirmPassword = new JPasswordField();
        lblUsername = new JLabel("Nombre de usuario:");
        txtUsername = new JTextField();
        btnForgotPassword = new JButton("¿Has olvidado tu contraseña?");
        btnLoginWithGoogle = new JButton("Iniciar sesión con Google");
        btnSubmit = new JButton("Enviar");

        // Agregar componentes al formulario
        add(lblEmail);
        add(txtEmail);
        add(lblPassword);
        add(txtPassword);
        add(lblConfirmPassword);
        add(txtConfirmPassword);
        add(lblUsername);
        add(txtUsername);
        add(btnForgotPassword);
        add(btnLoginWithGoogle);
        add(btnSubmit);

        // Registrar ActionListener para el botón de enviar
        btnSubmit.addActionListener(this);

        setVisible(true);
    }

    // Método para manejar eventos de botones
    public void actionPerformed(ActionEvent e) {
        if (e.getSource() == btnSubmit) {
            // Validar y procesar datos ingresados
            String email = txtEmail.getText();
            String password = new String(txtPassword.getPassword());
            String confirmPassword = new String(txtConfirmPassword.getPassword());
            String username = txtUsername.getText();

            // Aquí puedes realizar la validación y procesamiento adicional de los datos
            // Por ejemplo, verificar si las contraseñas coinciden, si el correo electrónico es válido, etc.
            
            // Muestra un mensaje de confirmación
            JOptionPane.showMessageDialog(this, "¡Registro exitoso!");
        }
    }

    public static void main(String[] args) {
        new Formulario();
    }
}
