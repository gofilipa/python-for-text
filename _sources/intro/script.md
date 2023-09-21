# opening script

We begin with a script as a kind of landmark for where the workshop will
go. By the end, you should be able to read the script and
understand how it works. (There is also a bug hidden in the code for the students to find.)

The text from this script is taken from the \"[Feminist Data
Manifest-NO](https://www.manifestno.com/home)\" by Marika Cifor, Patricia Garcia et al. This "Manifest-NO" is a statement of data ethics in a world where data practices are used to surveille, control, and extract value. The creators crucially demand that "data be acknowledged as at once an interpretation and in need of interpretation." 

``` python

text = ''' 
  1. We refuse to operate under the assumption that risk 
  and harm associated with data practices can be bounded to  mean 
  the same thing for everyone, everywhere, at every time. We commit 
  to acknowledging how historical and systemic patterns of violence 
  and exploitation produce differential vulnerabilities for 
  communities.
  2. We refuse to be disciplined by data, devices, and practices 
  that seek to shape and normalize racialized, gendered, and 
  differently-abled bodies in ways that make us available to be 
  tracked, monitored, and surveilled. We commit to taking back 
  control over the ways we behave, live, and engage with data and 
  its technologies.
  3. We refuse the use of data about people in perpetuity. We 
  commit to embracing agency and working with intentionality, 
  preparing bodies or corpuses of data to be laid to rest when they 
  are not being used in service to the people about whom they were 
  created.
  4. We refuse to understand data as disembodied and thereby 
  dehumanized and departicularized. We commit to understanding 
  data as always and variously attached to bodies; we vow to 
  interrogate the biopolitical implications of data with a keen 
  eye to gender, race, sexuality, class, disability, nationality, 
  and other forms of embodied difference.
  5. We refuse any code of phony “ethics” and false proclamations of 
  transparency that are wielded as cover, as tools of power, as forms 
  for escape that let the people who create systems off the hook from 
  accountability or responsibility. We commit to a feminist data 
  ethics that explicitly seeks equity and demands justice by helping 
  us understand and shift how power works.'''

sentence = text.split()

results = []
for sentence in text:
    if 'Refuse' in sentence:
    results.append(sentence)

print(results)


```