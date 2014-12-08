location-GUI
============
import java.awt.BorderLayout;
import java.awt.EventQueue;

import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.border.EmptyBorder;
import javax.swing.JLabel;
import javax.swing.JComboBox;
import javax.swing.JButton;
import java.awt.event.ActionListener;
import java.awt.event.ActionEvent;
import javax.swing.JTextField;


public class location extends JFrame {

	private JPanel contentPane;
	private JTextField textField;
	private JTextField textField_1;
	

	/**
	 * Launch the application.
	 */
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					location frame = new location();
					frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}

	/**
	 * Create the frame.
	 */
	public location() {
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setBounds(100, 100, 450, 300);
		contentPane = new JPanel();
		contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));
		setContentPane(contentPane);
		contentPane.setLayout(null);
		
		JLabel lblWhereAreYou = new JLabel("Where are you travelling from?");
		lblWhereAreYou.setBounds(6, 60, 206, 21);
		contentPane.add(lblWhereAreYou);
		
		JLabel lblDestination = new JLabel("Destination?");
		lblDestination.setBounds(297, 62, 147, 19);
		contentPane.add(lblDestination);
		
		JButton btnContinue = new JButton("Continue");
		btnContinue.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				String x = textField.toString();
				String y = textField_1.toString();
				welcome.tm.Schedule(y,x);
				welcome.tm.to =y;
				welcome.tm.from = x;
				System.exit(0);
				quantity.main(null);
				
				
			}
			
		});
		btnContinue.setBounds(162, 168, 117, 29);
		contentPane.add(btnContinue);
		
		textField = new JTextField();
		textField.setBounds(37, 91, 134, 28);
		contentPane.add(textField);
		textField.setColumns(10);
		
		textField_1 = new JTextField();
		textField_1.setBounds(264, 93, 134, 28);
		contentPane.add(textField_1);
		textField_1.setColumns(10);
	}
}
