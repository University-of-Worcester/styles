<!DOCTYPE html> 
<html lang="en-gb"> 
	<head>
<link rel="stylesheet" type="text/css" href="stylesheets/normalize.css" media="screen"> 
<link href='https://fonts.googleapis.com/css?family=Open+Sans:400,700' rel='stylesheet' type='text/css'> 
<link rel="stylesheet" type="text/css" href="stylesheets/stylesheet.css" media="screen"> 
<link rel="stylesheet" type="text/css" href="stylesheets/github-light.css" media="screen">
	<head>
<body>
<h1>Implementation Notes - Version 1.0</h1>
<b>Christopher Hill - 08/2015</b>
<p>
<b>Implementation Rationale</b> – The way I have chosen to approach the creation of this CSL Layout is from a philosophy of extensibility: Rather than have a format rule for every type of source, a generic layout has been defined based on the quantified, modal-average way in which the University of Worcester defines its layouts. Simply speaking, it caters to the lowest common denominator by displaying every attribute with a value provided, implementing rules on top of this for ‘special cases’. 
For example, most source types only list their year of publication, however, newspapers and broadcasts also require the month and day of month in their bibliography references. In such cases, a rule is defined that checks if the type is one of the aforementioned and if it is, adapts the layout accordingly.  
This system is especially useful when dealing with electronic sources. The CSL specification chooses not to differentiate whether a source is digital or physical on the basis that this should be inferred from its source location, such as a URL (and at the end of the day, the content is the same regardless). With an extensibility-based rule in place, if a source URL and date of access are provided with any source type, they will be displayed appropriately.
<p>
<b>Miscellaneous Implicit CSL Mapping Rules</b> – there are many rules that have been implemented in the current University of Worcester CSL style definition that do not explicitly map to the CSL specification: They are interpretations – decisions made by the style author – which may be incompatible with how some software handles sources, possibly affecting the output format. All of the mapping can be seen in the CSL Format Matrix with extra detail provided by comments. Some of the more nuanced rules and decisions are;
<li>If there is no Author provided, the title is used first, italicised, before the date of publication</li>
<li>The ‘original-title’ variable is used for work that was originally titled in another language, appearing after the standard title, italicised in square-braces</li>
<li>The ‘genre’ variable is used for attributes like “BA Hons” and other somewhat miscellaneous things</li>
<p>
<b>CSL Issues</b> – These are things included in the University of Worcester’s guide but currently not catered for by the CSL spec.
<li>No ability to parse the value of a variable in an individual source (only if it has a value or not). For example, this prevents the ability to distinguish Acts of Parliament prior to 1963 – which require a different format – because the actual value “1963” cannot be used in conditional logic.</li>
<li>Many of the variables for series/chapter/volume/issue etc. only accept a numeric value and not an alpha-numeric value such as “SKT27” </li>
</body>
</html>
