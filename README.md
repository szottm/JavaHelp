# JavaHelp
Beginner with Java, need help why Tomcat can't find files

This is the error message I get when I type in the URL:

HTTP Status 500 - Error instantiating servlet class CatalogPage

type Exception report

message Error instantiating servlet class CatalogPage

description The server encountered an internal error that prevented it from fulfilling this request.

exception

javax.servlet.ServletException: Error instantiating servlet class CatalogPage
	org.apache.catalina.valves.ErrorReportValve.invoke(ErrorReportValve.java:99)
	org.apache.catalina.valves.AccessLogValve.invoke(AccessLogValve.java:936)
	org.apache.catalina.connector.CoyoteAdapter.service(CoyoteAdapter.java:407)
	org.apache.coyote.http11.AbstractHttp11Processor.process(AbstractHttp11Processor.java:1004)
	org.apache.coyote.AbstractProtocol$AbstractConnectionHandler.process(AbstractProtocol.java:589)
	org.apache.tomcat.util.net.JIoEndpoint$SocketProcessor.run(JIoEndpoint.java:312)
	java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1142)
	java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:617)
	java.lang.Thread.run(Thread.java:745)
root cause

java.lang.InstantiationException
	sun.reflect.InstantiationExceptionConstructorAccessorImpl.newInstance(InstantiationExceptionConstructorAccessorImpl.java:48)
	java.lang.reflect.Constructor.newInstance(Constructor.java:422)
	java.lang.Class.newInstance(Class.java:442)
	org.apache.catalina.valves.ErrorReportValve.invoke(ErrorReportValve.java:99)
	org.apache.catalina.valves.AccessLogValve.invoke(AccessLogValve.java:936)
	org.apache.catalina.connector.CoyoteAdapter.service(CoyoteAdapter.java:407)
	org.apache.coyote.http11.AbstractHttp11Processor.process(AbstractHttp11Processor.java:1004)
	
	
	
	
	
	Any ideas on what to do? Here's my code for the page I'm trying to run
	
	/** Describes a catalog item for on-line store. The itemID
 *  uniquely identifies the item, the short description
 *  gives brief info like the book title and author,
 *  the long description describes the item in a couple
 *  of sentences, and the cost gives the current per-item price.
 *  Both the short and long descriptions can contain HTML
 *  markup.
 *  <P>
 *  Taken from Core Servlets and JavaServer Pages 2nd Edition
 *  from Prentice Hall and Sun Microsystems Press,
 *  http://www.coreservlets.com/.
 *  &copy; 2003 Marty Hall; may be freely used or adapted.
 */

public class CatalogItem {
  private String itemID;
  private String shortDescription;
  private String longDescription;
  private double cost;

  public CatalogItem(String itemID, String shortDescription,
                     String longDescription, double cost) {
    setItemID(itemID);
    setShortDescription(shortDescription);
    setLongDescription(longDescription);
    setCost(cost);
  }
    
  public String getItemID() {
    return(itemID);
  }

  protected void setItemID(String itemID) {
    this.itemID = itemID;
  }

  public String getShortDescription() {
    return(shortDescription);
  }

  protected void setShortDescription(String shortDescription) {
    this.shortDescription = shortDescription;
  }

  public String getLongDescription() {
    return(longDescription);
  }

  protected void setLongDescription(String longDescription) {
    this.longDescription = longDescription;
  }

  public double getCost() {
    return(cost);
  }

  protected void setCost(double cost) {
    this.cost = cost;
  }
}

	org.apache.coyote.AbstractProtocol$AbstractConnectionHandler.process(AbstractProtocol.java:589)
	org.apache.tomcat.util.net.JIoEndpoint$SocketProcessor.run(JIoEndpoint.java:312)
	java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1142)
	java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:617)
	java.lang.Thread.run(Thread.java:745)
note The full stack trace of the root cause is available in the Apache Tomcat/7.0.34 logs.
