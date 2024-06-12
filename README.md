
package application;
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.*;
import javafx.scene.layout.BorderPane;
import javafx.stage.Stage;

public class Main extends Application {

    public static void main(String[] args) {
        launch(args);
    }

    @Override
    public void start(Stage primaryStage) {
        primaryStage.setTitle("Barra de Menú en JavaFX");

        // Crear elementos de menú
        Menu archivoMenu = new Menu("Archivo");
        MenuItem abrirItem = new MenuItem("Abrir");
        MenuItem guardarItem = new MenuItem("Guardar");
        SeparatorMenuItem separador = new SeparatorMenuItem();
        MenuItem salirItem = new MenuItem("Salir");
        archivoMenu.getItems().addAll(abrirItem, guardarItem, separador, salirItem);

        Menu editarMenu = new Menu("Editar");
        MenuItem copiarItem = new MenuItem("Copiar");
        MenuItem pegarItem = new MenuItem("Pegar");
        editarMenu.getItems().addAll(copiarItem, pegarItem);

        Menu ayudaMenu = new Menu("Ayuda");
        MenuItem acercaDeItem = new MenuItem("Acerca de...");

        // Definir acciones para los elementos de menú
        abrirItem.setOnAction(e -> System.out.println("Abrir archivo"));
        guardarItem.setOnAction(e -> System.out.println("Guardar archivo"));
        salirItem.setOnAction(e -> primaryStage.close());
        copiarItem.setOnAction(e -> System.out.println("Copiar texto"));
        pegarItem.setOnAction(e -> System.out.println("Pegar texto"));

        // Crear la barra de menú
        MenuBar menuBar = new MenuBar();
        menuBar.getMenus().addAll(archivoMenu, editarMenu, ayudaMenu);

        // Organizar la interfaz con BorderPane
        BorderPane root = new BorderPane();
        root.setTop(menuBar);

        // Crear escena y mostrarla
        Scene scene = new Scene(root, 400, 300);
        primaryStage.setScene(scene);
        primaryStage.show();
    }
}

![image](https://github.com/stevenbetancourtuwu/stevenbetancourt/assets/172458170/8fb2fd4b-f382-49f1-bc2b-0188185c765e)

