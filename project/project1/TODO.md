TODO表单页面设计，包括前端和后端
package org.vaadin.marcus.spring;

import com.vaadin.flow.component.ClickEvent;
import com.vaadin.flow.component.UI;
import com.vaadin.flow.component.button.Button;
import com.vaadin.flow.component.html.H1;
import com.vaadin.flow.component.html.H4;
import com.vaadin.flow.component.orderedlayout.HorizontalLayout;
import com.vaadin.flow.component.orderedlayout.VerticalLayout;
import com.vaadin.flow.component.textfield.TextField;
import com.vaadin.flow.router.*;
import com.vaadin.flow.server.VaadinService;

import javax.servlet.http.Cookie;
import java.awt.*;

@Route("/")
public class Todo extends VerticalLayout implements AfterNavigationObserver{
  private   VerticalLayout todoList = new VerticalLayout();
   private TextField todoFiled = new TextField();
    public Todo() {
    Button addButton = new Button("Add");
     addButton.addClickListener(this::onAdd);


   add(new H1("TODO"),new H4("Hello"+getUserName()),new HorizontalLayout(todoFiled,addButton));

  }

   public  String getUserName(){

  for (Cookie cookie : VaadinService.getCurrentRequest().getCookies());{
           RouteParam cookie = null;
           if (cookie.getName().equals("username")){
                return cookie.getValue();
            }
       }

   return "";


   }


public  void  onAdd(ClickEvent event){

   String todoVal = todoFiled.getValue();
    Checkbox checkbox = new Checkbox(todoVal);
        todoList.add(String.valueOf(checkbox));
}
    @Override
    public void afterNavigation(AfterNavigationEvent afterNavigationEvent) {

  for (Cookie cookie : VaadinService.getCurrentRequest().getCookies()) {
            if (cookie.getName().equals("username")){
                return;
            }
        }

  getUI().ifPresent(ui -> {
          ui.navigate("/login.html");
        });

 }
}
